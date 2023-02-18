<template>
  <v-app id="inspire">
    <v-navigation-drawer
      v-model="drawer"
      temporary
      class="bg-deep-purple"
      theme="dark"
      >
      <!--  -->
      <v-list color="transparent">
        <v-list-item
          prepend-avatar="https://randomuser.me/api/portraits/men/78.jpg"
          title="John Leider"
        ></v-list-item>
      </v-list>

        <v-divider></v-divider>
      <v-list
        :lines="false"
        nav
      >
        <v-list-item
          v-for="item in items"
          :key="item.title"
          link
        >

        <template v-slot:prepend>
          <v-icon :icon="item.icon"></v-icon>
        </template>

        <v-list-item-title v-text="item.title"></v-list-item-title>
        </v-list-item>

      </v-list>
      <template v-slot:append>
          <div class="pa-2">
            <v-btn block>
              Logout
            </v-btn>
          </div>
        </template>
    </v-navigation-drawer>

    <v-app-bar>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-toolbar-title>Vuetify Sample Pages</v-toolbar-title>
    </v-app-bar>

    <v-main>
      <!--  -->

    </v-main>
  </v-app>
</template>

<script>
  export default {
    data: () => ({
       drawer: null,
       items: [
        { title: 'Dashboard', icon: 'mdi-view-dashboard'},
        { title: 'Account', icon: 'mdi-account-box'},
        { title: 'Todo', icon: 'mdi-gavel'},

      ],
    }),
  }
</script>

