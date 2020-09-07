<template>
  <v-app>
    <v-row align="center" justify="space-around">
      <router-link to="/">Home</router-link>|
      <router-link to="/primero">Primer Proyecto</router-link>|
      <router-link to="/segundo">Segundo Proyecto</router-link>|
      <router-link to="/tercero">Tercero Proyecto</router-link>|
      <router-link to="/todo">Todos los Proyectos</router-link>
    </v-row>
    <v-main>
      <router-view />
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: "App",

  components: {},

  data: () => ({
    //
  })
};
</script>
