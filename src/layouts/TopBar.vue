<template>
  <div>
    <v-app-bar
      :clipped-left="clipped"
      fixed
      color="white"
    >
     

    
      <v-app-bar-nav-icon @click="drawer = true" class="hidden-md-and-up"></v-app-bar-nav-icon>
<nuxt-link to="/">
        <v-toolbar-title link @click="changeRoute()">
          <img
            :src="require('../assets/logo.png')"
            width="150"
            class="mt-2 ml-5"
            lazy-load
          />
        </v-toolbar-title>
      </nuxt-link>

<v-toolbar class="hidden-sm-and-down elevation-0" color="transparent">

   
      <v-spacer></v-spacer>
        
      <v-toolbar-items class="hidden-sm-and-down">
       
          <v-btn
            class="black--text text-capitalize"
            v-bind="attrs"
            v-on="on"
            text
            to="/"
          >
            Home
          </v-btn>
       
      <!-- <v-btn class="black--text text-capitalize" text to="/data-annotation">
      Courses
      </v-btn> -->

      <v-btn text class="mx-5 text-capitalize" to="/teachers">Teachers</v-btn>

      <v-btn text class="mx-5">Contact Us</v-btn>

            <v-spacer></v-spacer>

      <!-- <v-img :src="require('../assets/flag.webp')" width="60" height="30" lazy-load color="#1AA15F" class="mt-4"
        ></v-img
      > -->
      </v-toolbar-items>
     
    </v-toolbar>


    </v-app-bar>

    <v-navigation-drawer class="back1" v-model="drawer" absolute temporary>

      <v-list-item link to="/">

<v-list-item-content>
  <v-list-item-title
    class=" text-left align-self-center"
    >Home</v-list-item-title
  >
</v-list-item-content>
</v-list-item>
      <v-list-item link to="/teachers">

<v-list-item-content>
  <v-list-item-title
    class=" text-left align-self-center"
    >Teachers</v-list-item-title
  >
</v-list-item-content>
</v-list-item>







      <v-list-item link to="/cross-platform-appDevelopment" >
             
             <v-list-item-content>
               <v-list-item-title
                 class=" text-left align-self-center"
                 >Courses</v-list-item-title
               >
             </v-list-item-content>
           </v-list-item>
     <!-- <v-list-group>
            <template v-slot:activator>
              
              <v-list-item-title class=" text-left align-self-center"
              to="/"  >Home</v-list-item-title
              >
            </template>
            
           
            <v-list-item link to="/shopify-ecommerce-development">

              <v-list-item-content>
                <v-list-item-title
                  class=" text-left align-self-center"
                  >Schedule and Fee</v-list-item-title
                >
              </v-list-item-content>
            </v-list-item>
            <v-list-item link to="/devOpps-agile-excellence">

              <v-list-item-content>
                <v-list-item-title
                  class=" text-left align-self-center"
                  >Contact Us</v-list-item-title
                >
              </v-list-item-content>
            </v-list-item>
          </v-list-group>
          <v-list-item link to="/data-annotation">
            
            <v-list-item-title class=" text-left align-self-center"
              >Computer Vision AI</v-list-item-title
            >
          </v-list-item>
          <v-list-item link to="/about">
           
            <v-list-item-title class=" text-left align-self-center"
              >About Us</v-list-item-title
            >
          </v-list-item> -->
     
    </v-navigation-drawer>
  </div>
</template>
<script>
export default {
  data() {
    return {
      drawer: false,
      dashboardButton: false,
      buttons: [
        {
          title: "Men’s Clothing",
          id: 1,
        },
        {
          title: " Women’s Clothing",
          id: 2,
        },
        {
          title: " Tech & Gadgets",
          id: 3,
        },
        {
          title: " Health & Wellness",
          id: 4,
        },
        {
          title: " Pets",
          id: 5,
        },
        {
          title: " Home Goods",
          id: 5,
        },
        {
          title: " Food & Beverage",
          id: 6,
        },
      ],
    };
  },
  methods: {
    openModal() {
      this.$emit("openDialog", true);
    },
    changeRoute() {
      this.$router.push({ path: "/" });
    },
  },
  
};
</script>

<style scoped></style>
