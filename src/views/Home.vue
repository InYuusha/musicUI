<template>
<v-app id="inspire" :style="{background:$vuetify.theme.themes.dark.background}">
  <SideBar/>
</v-app>
</template>

<script>
// @ is an alias to /src
import SideBar from '../components/SideBar.vue'

export default {
  name: 'Home',
  components: {
    SideBar
  }
}
</script>
