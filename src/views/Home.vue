<template>
<v-app id="inspire" :style="{background:$vuetify.theme.themes.dark.background}">
  <SideBar/>
  <v-container>
    <v-app-bar color="rgba(0,0,0,0)" flat class="mt-4">
      <v-row>
        <v-col cols="1" sm="3">
          <v-btn color="orange" outlined dark>
            <v-icon left>fas fa-upload</v-icon>Upload
          </v-btn>
        </v-col>

        <v-col cols="3" sm="6" >
          <v-text-field label="Search..." filled append-icon="mdi-magnify" dense solo flat background-color="#1E2337" dark></v-text-field>
        </v-col> 

        <v-col cols="6" sm="3" >
          <div class="float-right mt-n1">
            <v-btn icon dark class="mr-n8">
              <v-icon color="#878A94">fas fa-bell</v-icon>
            </v-btn>
            <v-btn icon dark>
              <v-badge bordered overlap color="red" dot class="mr-n8">
                <v-icon  color="#878A94">fas fa-envelope</v-icon>
              </v-badge>
            </v-btn>
            <v-btn text color="#878A94">Aperio</v-btn>
            <v-avatar size="30" class="ml-n3">
              <v-img src="https://cdn.vuetify.com/images/lists/4.png"></v-img>
            </v-avatar>
            <v-btn icon dark class="ml-1">
              <v-icon x-small color="#878A94">fas fa-chevron-down</v-icon>
            </v-btn>
          </div>
        </v-col>
      </v-row>
    </v-app-bar>
    <div class="d-flex flex-column justify-space-between align-center">
      <v-app-bar class="" color="#2F3346" flat>
        <v-icon color="#878A94">fas fa-caret-left</v-icon>
        <span class="ml-3 mr-3 white--text">Until The Sun Comes Up LP</span>
        <v-icon color="#878A94">fas fa-caret-right</v-icon>
      </v-app-bar>
    </div>
    <Carousel-3d :controlsVisible="true" :clickable="true" :height="300">
       <slide :index="i" :key="i" v-for="(slide,i) in slides">
         <figure>
           <img :src="slide.src"/>
           <figcaption>
             <v-btn text color="white">{{slide.text}}</v-btn>
           </figcaption>
         </figure>
       </slide>
    </Carousel-3d>
   
  </v-container>
</v-app>
</template>

<script>
// @ is an alias to /src
import SideBar from '../components/SideBar.vue'
import {Carousel3d,Slide} from "vue-carousel-3d"

export default {
  name: 'Home',
  components: {
    SideBar,
    Carousel3d,
    Slide
  },
  data:()=>({
    slides:[
      {src:'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTtr9GKwdSTWOcOBl3xoglB2YudxKGXNPyI0A&usqp=CAU',text:'90s Pop'},
      {src:'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSwAnDl0FRUvYL_t0nwokBe8C-41qQvzXs3Qw&usqp=CAU',text:'Madona'},
      {src:'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSU08e8adYzrpcl7-_AwUwaXUK_aF3EMev8HQ&usqp=CAU',text:'Justin Bieber'},
    ]
  })
}
</script>

<style scoped>
.carousel-3d-container figure{
  margin:0;
}
.carousel-3d-container figcaption{
  position:absolute;
  background-color:rgba(0,0,0,0.5);
  color:white;
  bottom:0;
  position:absolute;
  padding:15;
  font-size:12;
  min-width:100%;
  box-sizing:border-box;
}
.next span, .prev span{
  color:orange;
}

</style>
