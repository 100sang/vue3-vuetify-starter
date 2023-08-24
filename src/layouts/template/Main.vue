<template>
  <v-app :theme="this.$store.state? this.$store.state.theme : 'light'"> 
     Demo Main
  </v-app>
</template>

<script setup>
import Header from './AppBar.vue'
import Sidebar from './SideBar.vue'
import Toolbar from './Tools.vue'
import Contents from './Content.vue'
import Footer from './Footer.vue'

import Gallery from '@/components/Gallery.vue'
import List from '@/components/List.vue'
</script>
