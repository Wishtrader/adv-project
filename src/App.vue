<template>
  <v-app>

    <v-navigation-drawer app temporary
    v-model="drawer"
    >
      <v-list>
        <v-list-tile
          v-for="link in links"
          @click="0"
          :key="link.title"
          :to="link.url"
        >
          <v-list-tile-action>
            <v-icon>{{link.icon}}</v-icon>
          </v-list-tile-action>

          <v-list-tile-content>
            <v-list-tile-title v-text="link.title"></v-list-tile-title>
          </v-list-tile-content>
         
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>

    <v-toolbar app dark color="primary">
      <v-toolbar-side-icon
        class="hidden-md-and-up" 
        @click="drawer = !drawer"
      ></v-toolbar-side-icon>
      <v-toolbar-title>
        <router-link to="/" tag="span" class="pointer">Add Aplication</router-link>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-items class="hidden-sm-and-down">
        <v-btn flat
          v-for="link in links"
          :key="link.title"
          :to="link.url"
        >
          <v-icon left>{{link.icon}}</v-icon>
          {{link.title}}
        </v-btn>
      </v-toolbar-items>
    </v-toolbar>

    <v-content>
      <router-view></router-view>
    </v-content>

  </v-app>
</template>

<script>
export default {
  data () {
    return {
      drawer: false,
      links: [
        { icon: 'lock', title: 'Login', url: '/login' },
        { icon: 'face', title: 'Registration', url: '/registration' },
        { icon: 'bookmark_border', title: 'Orders', url: '/orders' },
        { icon: 'note_add', title: 'New advertising', url: '/new' },
        { icon: 'list', title: 'My advertising', url: '/list' }
      ]
    }
  }
}
</script>

<style scoped>

.pointer {
  cursor: pointer;
}

</style>
