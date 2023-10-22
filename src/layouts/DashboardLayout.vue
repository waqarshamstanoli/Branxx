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

export default {
  components: {
    DashboardContent,
    TopBar,
    Footer,
  },

  data() {
    return {
      
    };
  },
  
};
</script>

<style lang="scss">

</style>
