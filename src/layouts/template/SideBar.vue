<template>
   <div>
   <v-navigation-drawer
        v-model="drawer"
        :rail="rail"
        permanent
        @click="rail = false"
      >
        <v-list-item
          title="My Name"
          :subtitle="email"
          nav
        >
             <template v-slot:prepend>
           <v-avatar
              color="grey-darken-2"
            >
              <span class="text-h6">MJ</span>
          </v-avatar>
          </template>
          <template v-slot:append>
            <v-btn
              variant="text"
              icon="mdi-chevron-left"
              @click.stop="rail = !rail"
            ></v-btn>
          </template>
        </v-list-item>

      <v-divider></v-divider>


      <v-list density="compact" nav>

        <v-list-item
          v-for="item in menus"
          :key="item.title"
          :value="item.value"
          :title="item.title"
        >
          <template v-slot:prepend>
            <v-icon :icon="item.prependIcon"></v-icon>
          </template>
        </v-list-item>

        <v-list-item
          v-for="n in 3"
          :key="`menu`+n"
          :value="n+3"
        >
          <template v-slot:prepend>
            <v-icon icon="mdi-circle"></v-icon>
          </template>

          <v-list-item-title>menu {{n}}</v-list-item-title>
        </v-list-item>

      </v-list>
    </v-navigation-drawer>


    <v-navigation-drawer permanent>
       <v-sheet
        color="sheet"
        height="128"
        width="100%"
      ></v-sheet>

      <v-list :items="submenus"></v-list>

    </v-navigation-drawer>


    </div>
</template>

<script>
export default {
  data () {
      return {
        drawer: true,
        email : this.$store.state.email,
        menus: [
          { title: 'My Files', value: 1, prependIcon: 'mdi-folder'},
          { title: 'Shared with me', value: 2, prependIcon: 'mdi-account-multiple'},
          { title: 'Starred', value: 3, prependIcon: 'mdi-star'},
        ],
        submenus: [
            { type: 'subheader', title: 'Menu Group1' },
            { title: 'Item #1', value: 1, },
            { title: 'Item #2', value: 2, },
            { title: 'Item #3', value: 3, },
            { type: 'divider' },
            { type: 'subheader', title: 'Menu Group2' },
            { title: 'Item #4', value: 4, },
            { title: 'Item #5', value: 5, },
            { title: 'Item #6', value: 6, },
            { type: 'divider' },
        ],
        rail: true,
      }
  }
}
</script>

<style>

</style>