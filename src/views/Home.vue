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
    <div class="d-flex flex-column justify-between align-center">
      <v-app-bar class="" color="#2F3346" flat>
        <v-btn text class="ml-2 white--text">
          <v-icon left dark color="#878A94">fas fa-caret-right</v-icon>
          2.54M Listeners
        </v-btn>
        <v-btn dark color="orange">
          <v-icon left dark >fas fa-heart</v-icon>
          1.2M Likes
        </v-btn>
        <v-btn color="#1E2337" dark class="ml-2">
          <v-icon left dark>fas fa-retweet</v-icon>
          201K Reposts
        </v-btn>
        <v-btn color="#1E2337" dark class="ml-2">
          <v-icon left dark>fas fa-share-square</v-icon>
          Share 
        </v-btn>
        <v-btn color="1E2337" dark class="ml-2">
          <v-icon left dark>fas fa-ellipsis-h</v-icon>
          More
        </v-btn>
      </v-app-bar>
    </div>
    <div class="d-flex flex-column justify-space-between align-center">
        <v-row>
          <v-col cols="12" sm="2"></v-col>
          <v-col cols="12" sm="8" style="position:absolute;bottom:0;
          margin-left:auto;margin-right:auto;left:0;right:0;text-align:center">
            <v-card title color="#1E2337" dark>
                <v-progress-linear :value="50" class="my-0" height="3"></v-progress-linear>
                  <v-row>
                    <v-col cols="3" sm="2">
                      <v-img src="https://static.displate.com/280x392/displate/2020-01-18/0f7ea827e6c9134140bf1832acc69480_fe8418eefc7d7b64bd5be271c7c919e2.jpg" max-height="60" max-width="50" class="mt-6 ml-4"></v-img>
                    </v-col>
                    <v-col cols="6" sm="2">
                      <h6 class="mt-5 ml-n16 grey--text text--lighten">La liberte</h6><br>
                      <span clas="grey--text text-darken-2">Soolking</span>
                    </v-col>
                    <v-col cols="6" sm="2">
                      <v-btn icon class="ml-n14 mt-4">
                        <v-icon>mdi-rewind</v-icon>
                      </v-btn>
                      <v-btn icon class="mt-4">
                        <v-icon color="orange">mdi-pause</v-icon>
                      </v-btn>
                      <v-btn icon class=" mt-4">
                        <v-icon>mdi-fast-forward</v-icon>
                      </v-btn>
                    </v-col>
                  </v-row>
            </v-card>
          </v-col>
        </v-row>
      </div>
   
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
