<template>
  <v-app id="inspire">
    <v-navigation-drawer v-model="drawer" app clipped>
      <v-list dense>
        <!-- MENU PRIMERO -->
        <v-list-item to="/primero">
          <v-list-item-action>
            <v-icon>mdi-numeric-1-box</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Primer Ejercicio</v-list-item-title>
          </v-list-item-content>
        </v-list-item>

        <!-- MENU SEGUNDO -->
        <v-list-item to="/segundo">
          <v-list-item-action>
            <v-icon>mdi-numeric-2-box</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Segundo Ejercicio</v-list-item-title>
          </v-list-item-content>
        </v-list-item>

        <!-- MENU TERCERO -->
        <v-list-item to="/tercero">
          <v-list-item-action>
            <v-icon>mdi-numeric-3-box</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Tercer Ejercicio</v-list-item-title>
          </v-list-item-content>
        </v-list-item>

        <!-- MENU TODOS -->
        <v-list-item to="/todo">
          <v-list-item-action>
            <v-icon>mdi-view-dashboard</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Todos los Ejercicios</v-list-item-title>
          </v-list-item-content>
        </v-list-item>

        <!-- MENU FOMULARIO -->
        <v-list-item to="/formulario">
          <v-list-item-action>
            <v-icon>mdi-beta</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Formulario</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <!-- INICIALIZACION DE BARRA -->
    <v-app-bar app clipped-left>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
      <router-link to="/" tag="v-icon">
        <v-icon>mdi-home</v-icon>
      </router-link>
      <v-toolbar-title>Home</v-toolbar-title>
    </v-app-bar>

    <!-- INICIALIZACION DE MAIN -->
    <v-main>
      <v-container class="fill-height" fluid>
        <v-row align="center" justify="center">
          <v-col>
            <router-view />
          </v-col>
        </v-row>
      </v-container>
    </v-main>

    <!-- INICIALIZACION DE FOOTER -->
    <v-footer app>
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: "App",

  components: {},

  data: () => ({
    drawer: null
  }),
  created() {
    this.$vuetify.theme.dark = true;
  }
};
</script>
