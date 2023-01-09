<template>
    <v-app-bar
      color="primary"
      density="compact"
      :elevation="2"
    >
      <template v-slot:prepend>
        <v-app-bar-nav-icon></v-app-bar-nav-icon>
      </template>

      <v-app-bar-title>{{this.$store.state.project}}</v-app-bar-title>

      <template v-slot:append>

          <v-btn dark icon @click="onClick">
            <v-icon :icon="theme === 'light' ? 'mdi-weather-sunny' : 'mdi-weather-night'" />
             <v-tooltip
              activator="parent"
              location="bottom"
            >{{ $filters.capitalize(theme)  }} Theme</v-tooltip>
          </v-btn>

          <v-divider
              class="my-2 mx-3"
              vertical
          ></v-divider>

         <v-btn dark icon
           v-for="item in icons"
           :key="item.text">
            <v-icon>{{item.icon}}</v-icon>
            <v-tooltip
              activator="parent"
              location="bottom"
            >{{item.text}}</v-tooltip>
          </v-btn>    

      </template>
    </v-app-bar>
</template>


<script>
export default {
  data () {
      return {
       icons : [
        {text : 'Settings', icon : 'mdi-cog'},
        {text : 'Notifications', icon : 'mdi-bell'}
      ]
     }
  },
  computed: {
    theme() {
      return this.$store.state.theme
    }
  },
  methods : {
    onClick () {
       this.$store.state.theme =  this.$store.state.theme === 'light' ? 'dark' : 'light'
    }
  }
}

</script>
