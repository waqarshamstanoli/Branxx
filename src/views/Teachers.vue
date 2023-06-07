<template>
    <v-container>
        <v-row>
            <v-col cols="12" lg="12" md="12" sm="12" >
            <h1 class="text-center">Our Experts Team Member
</h1>
            </v-col>
            <v-col cols="12" lg="3" md="6" sm="6" v-for="teacher in teachers" :key="teacher">
  <v-hover>
    <template v-slot:default="{ hover }">
    <v-avatar size="300"> 
        <v-img :src="require('../assets/qari.png')"  lazy-load></v-img>
         <transition name="slide-fade">
          <v-overlay
            v-if="hover"
            absolute
            color="accent"
            opacity=0.9
            z-index="4"
          >
           <h2 class="text-center">{{ teacher.name }}
</h2>
           <h5 class="text-center">{{ teacher.designation }}</h5>
           <h5 class="text-center">Experience:  {{ teacher.experience }}</h5>
          </v-overlay>
        </transition>
    </v-avatar></template>
  </v-hover>
  
</v-col>

        </v-row>
    </v-container>
</template>
<script>
export default {
    data(){
        return {
teachers:[
    {
        name:'Muhammad Tahir',
        designation:'Director Altahir Academy',
        experience:'22 years'
    },
    {
        name:'Muhammad Javed',
        designation:'',
        experience:'9 years'
    },
    {
        name:'Habiullah',
        designation:'',
        experience:'16 years'
    },
    {
        name:'Muhammad Naeem',
        designation:'',
        experience:'8 years'
    },
    {
        name:'Muhammad Nawab',
        designation:'',
        experience:'22 years'
    },
    {
        name:'Muhammad Ashfaq',
        designation:'Qari Translation',
        experience:'22 years'
    },
      
]
        }
    }
}
</script>
<style>
.borderRadius {
  border-radius: 50px !important;
}
</style>