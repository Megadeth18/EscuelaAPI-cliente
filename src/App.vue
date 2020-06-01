<template>
  <v-app>
    <v-container></v-container>
    <v-container></v-container>
    <v-navigation-drawer app  v-model="drawer" class="blue darken-3">
      <v-list dense>
        <v-list-item >
          <v-list-item-content >
            <v-container></v-container>
            <v-list-item-title>
              CRUD
            </v-list-item-title>
            <v-list-item-subtitle>
              Inscripciones
            </v-list-item-subtitle>
            <v-container></v-container>
          </v-list-item-content>
        </v-list-item>
        <v-divider class="grey darken-4"></v-divider>
        <v-container></v-container>
        <v-list-item  color="blue lighten-5" v-for="item in items" :key="item.title"  link route :to="item.route">
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar app color="blue darken-4" dark hide-on-scroll scroll-target="#scrolling-techniques-4">
      <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
      <v-toolbar-title>CRUD</v-toolbar-title>
      <v-spacer></v-spacer>
    </v-app-bar>
    <v-content>
      <v-container fluid>
        <router-view></router-view>
      </v-container>
    </v-content>

  </v-app>
</template>

<script>
  export default {
    name: "App",
    data: () => ({
      items: [
        { title: "Estudiantes", icon: "mdi-account-group" , route: "/estudiantes"},
        { title: "Cursos", icon: "mdi-bookshelf" , route: "/cursos" },
      ],
      drawer: false,
    }),
    created () {
      this.$vuetify.theme.dark = true
    },
  };
</script>


