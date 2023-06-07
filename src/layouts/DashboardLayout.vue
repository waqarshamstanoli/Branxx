<template>
  <div class="dashboard-layout">
    <div class="">
      <Top-bar @openDialog="userModal = true"></Top-bar>

      <dashboard-content></dashboard-content>

      <Footer class="mt-8"></Footer>
    </div>

   
  
  
  </div>
</template>

<script>
import DashboardContent from "../components/ContentView.vue";
import TopBar from "../layouts/TopBar.vue";
import Footer from "./Footer.vue";
import { mapActions } from "vuex";

export default {
  components: {
    DashboardContent,
    TopBar,
    Footer,
  },

  data() {
    return {
      toggle: true,
      userModal: false,
      loginModal: false,
      forgotPasswordModal: false,
      showDialog: false,
      signUpData: { email: "", password: "" },
      loginData: { email: "", password: "" },
    };
  },
  methods: {
    ...mapActions(["registerUser", "loginUser"]),
    signUp() {
      this.registerUser(this.signUpData)
        .then((response) => {
          if (response.data.errors) {
            // alert(response);
            setTimeout(() => {
              // this.errors = {};
            }, 5000);
          } else {
            localStorage.setItem("access_token", response.data.token);
            // this.loading = false;
            this.$emit("requestStatus", response.data.msg);
          }
        })
        .finally(() => {
          // this.$emit("overlay", false);
        });
    },
    login() {
      this.loginUser(this.loginData)
        .then((response) => {
          if (response.data.errors) {
            alert(response);
            setTimeout(() => {
              // this.errors = {};
            }, 5000);
          } else {
            // this.loading = false;
            this.$emit("requestStatus", response.data.msg);
            localStorage.setItem("access_token", response.data.token);
            if(response.data.user.role==='admin'){
              localStorage.setItem("roleAdmin", response.data.user.role);
              this.$router.push({name:'admin'})
            }
          }
        })
        .finally(() => {
          // this.$emit("overlay", false);
        });
    },
    showLogin() {
      this.userModal = false;
      this.loginModal = true;
      this.forgotPasswordModal = false;
    },
    showSignup() {
      this.userModal = true;
      this.loginModal = false;
      this.forgotPasswordModal = false;
    },

    showForgotPassword() {
      this.userModal = false;
      this.loginModal = false;
      this.forgotPasswordModal = true;
    },
  },
};
</script>

<style lang="scss">

</style>
