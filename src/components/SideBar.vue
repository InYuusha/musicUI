<template>
  <v-navigation-drawer app color="#1E2337" dark>
      <div class="text-center mt-5">
          <v-icon x-large>fab fa-soundcloud</v-icon>
          <v-btn class="mt-3" text color="" outlined>
              Get SoundCloud Pro
          </v-btn>
      </div>
      <h4 class="mt-6 ml-5 white--text">For You</h4>
      <v-list flat dense class="mt-5">
          
      </v-list>
  </v-navigation-drawer>
</template>

<script>
export default {
    data:()=>({
        items:[
            {icon:'fas fa-satellite-dish',text:'Discover'},
            {icon:'fas fa-stream',text:'Stream'},
            {icon:'fas fa-user',text:'Communnity'},
            {icon:'fas fa-chart-pie',text:'Analytics'}
        ],
        collections:[
            {icon:'fas fa-heart',text:'Likes',route:'/likes'},
            {icon:'fas fa-music',text:'Playlists',route:'/playlists'},
            {icon:'fas fa-compact-disc',text:'Albums',route:'/albums'},
            {icon:'fas fa-podcast',text:'Podcasts',route:'/podcasts'},
            {icon:'fas fa-users',text:'Following',route:'/followings'}
        ]
    })
}
</script>

<style>
.border{
    border-right:4px solid orange;
}
</style>