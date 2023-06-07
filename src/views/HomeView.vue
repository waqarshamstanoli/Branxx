<template>
  <div class="home">
    <div>
  
  <v-img :src="require('../assets/11.jpg')"  height="600" lazy-load>
  <v-container>
   <v-row>
     <v-col cols="12" lg="6" offset-lg="6">
       <div class="box" color="transparent">
<!-- <h1 class="white--text">Quran Courses for everyone</h1> -->
<h1 class="white--text">
  The best of you are those who learn the Quran and teach it 
</h1>
<h6 class="white--text"> Ṣaḥīḥ al-Bukhārī 5027</h6>
</div>
<!-- <v-btn tile class="accent text-capitalize white--text mt-5">Get in Touch</v-btn> -->
     </v-col>
   </v-row>
   </v-container>
  </v-img>
<v-container>
 <v-row>
   <v-col cols="12" lg="4" md="6" sm="6" offset-lg="1">
     <v-img :src="require('../assets/1.jpg')" class="mt-16" width="500" lazy-load></v-img>
   </v-col>
   <v-col cols="12" lg="4" md="6" sm="6" offset-lg="1">
     <h1 class="mt-16">Learn Quran Online with Tajweed - Online Quran classes for Kids & Adults</h1>
     <h4 class="body-1">At Al Tahir Academy, our mission is to enrich the lives of Muslims by offering an affordable and accessible method for children 
      and adults to learn Quran online conveniently at home. The lessons of the Quran bring the greatest joy to Muslims that have gained a full and nuanced
       understanding of the texts through the learning of Tajweed and Tarteel.

That’s why we’ve dedicated ourselves to developing the most effective methods to help students learn to read and recite the Quran properly, with interactive
 online options that make learning Quran accessible. Our highly trained and experienced teachers will guide you or your kids through personalized sessions that 
 bring the great joy of devotion to the Quran into your home.</h4>
   </v-col>
    <v-col cols="12" lg="4" md="6" sm="6" offset-lg="1">
     <h1 class="mt-16">Online Quran Classes with Tajweed For Adults and Children
</h1>
     <h4 class="body-1 mr-12">The responsibilities of modern life make it difficult for many Muslims to devote as much time as they would like to study the Quran. 
      That’s why we offer so many different ways to learn the Quran online that can be adapted to the amount of time you have available, your area of interest, 
      and the type of teacher you prefer. We offer a wide range of classes that can fit into even the busiest schedules, providing a haven of devotion to Quran.

Learning the Quran online will give you the comfort that flows from the knowledge that you’re on the righteous path. That’s why our engaging, interesting and 
effective classes are so popular in over ninety countries around the world, spreading the love of the Quran. We offer free trial lessons to help you find the courses 
and instructors that are the best fit for your Quran learning needs and interests. 
Once you’ve chosen the teachers and subjects you prefer, you can register for Quran classes.</h4>
   </v-col>
   <v-col cols="12" lg="4" md="6" sm="6" offset-lg="1">
     <v-img :src="require('../assets/2.webp')" class="mt-16" lazy-load width="500"></v-img>
   </v-col>
   <!-- <v-col cols="12" lg="12" md="12" sm="12">
     <h1 class="text-center">Our Clients</h1>
     
   </v-col> -->
  
<!-- <v-col cols="12" lg="4" md="12" sm="12">
<v-card class="borderRadius mt-16" height="600">
      <div class="text-center mt-10">
     <span ><v-icon >mdi-calendar </v-icon>13 may, 2018</span>
</div>
     
     <v-card-text>
       <h3 class="text-center black--text">HEADLESS E-COMMERCE- Is It the future of e-commerce????</h3>
       <h4 class="body-2 mt-5">As a Customer, Do you want to shop online with ease?
          Are you a fan of eye-catching smart gadgets such as smart-watches 
          and want the freedom, flexibility, and convenience of shopping with 
          just one click? As a Seller, Sell faster. Sell better. Sell more.”Sell 
          anything in seconds 
         – in person, online, on any screen. Sell</h4>
     </v-card-text>
  </v-card>
   </v-col> -->
    <!-- <v-col cols="12" lg="4" md="12" sm="12">
<v-card class="borderRadius mt-16" height="600">
      <div class="text-center mt-10">
     <span ><v-icon >mdi-calendar </v-icon>13 may, 2018</span>
</div>
     
     <v-card-text>
       <h3 class="text-center black--text">Ähdus ERP App for Shopify businesses for Inventory management</h3>
       <h4 class="body-2 mt-5">With every small business going online, there is a strong need to manage products inventory from ERP system to the online store a business is running. Since our Shopify experts design, develop and maintain beautiful Shopify e-commerce stores for several clients worldwide, we also develop Shopify apps to 
         facilitate the individual needs of our customers. […]</h4>
     </v-card-text>
  </v-card>
   </v-col>
    <v-col cols="12" lg="4" md="12" sm="12">
<v-card class="borderRadius mt-16" height="600">
     <div class="text-center mt-10">
     <span ><v-icon >mdi-calendar </v-icon>13 may, 2018</span>
</div>
     
     <v-card-text>
       <h3 class="text-center black--text">How Ähdus Technology is building an IoT based Security Intelligent system</h3>
       <h4 class="body-2 mt-5">ÄHDUS TECHNOLOGY Joins Hands with Connect Security Solutions as their IT partner for an “Intelligent IoT based Security Solutions” About Connect Security Solutions Connect Security solutions, founded in 2004 have for many years been at the leading edge of patrol andworkforce management solutions. They are proud trusted suppliers of the world’s leading security andFacilities</h4>
     </v-card-text>
  </v-card>
   </v-col> -->
 </v-row>
 </v-container>

</div>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'HomeView',
  components: {
    HelloWorld
  }
}
</script>
<style>
.box {
  height: 320px;
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: middle; /* vertically aligns items */
  font-size:40px
  
}
</style>
