<template>
  <v-container>
    <!-- TITULO -->
    <h1 align="center">{{ mensaje }}</h1>

    <!-- INPUT -->
    <v-text-field
      v-model="datoUno"
      label="Inserta Texto"
      hint="Este texto se agregará al Título"
      outlined
      rounded
      filled
      clearable
    ></v-text-field>

    <v-row align="center" justify="space-around">
      <!-- BOTON AGREGAR -->
      <v-btn @click="agregar(datoUno)" text color="primary">
        Agregar
        <v-icon dark right>mdi-plus</v-icon>
      </v-btn>

      <!-- BOTON RESET -->
      <v-btn @click="reset()" text color="error">
        Reset
        <v-icon dark right>mdi-refresh</v-icon>
      </v-btn>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      mensaje: "Hola mundo ",
      datoUno: null
    };
  },
  methods: {
    agregar(datoUno) {
      if (datoUno != null) {
        this.mensaje = this.mensaje + this.datoUno;
      }
    },
    reset() {
      this.mensaje = "Hola mundo";
    }
  }
};
</script>

<style>
</style>