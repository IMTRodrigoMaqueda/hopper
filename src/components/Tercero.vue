<template>
  <v-container>
    <!-- TITULO -->
    <h1 align="center">Ahora me ves, ahora no me ves.</h1>
    <v-row align="center" justify="space-around">
      <v-col align-self="center" justify="space-around">
        <v-row align="center" justify="space-around">
          <!-- SWITCH O CHECK -->
          <v-switch v-model="status" label="Haz click"></v-switch>
        </v-row>
      </v-col>

      <v-col align-self="center" justify="space-around">
        <v-row align="center" justify="space-around">
          <!-- AGREGAR IMAGEN -->
          <v-img
            v-if="status"
            src="https://image.winudf.com/v2/image1/ZnJlZXRpcHMuaG93dG8uYW1vbmd1c190aXBzX2ljb25fMTU3ODU3MzA2OF8wMzU/icon.png?w=170&fakeurl=1"
            max-width="125"
          ></v-img>
        </v-row>

        <v-row align="center" justify="space-around">
          <!-- AGREGAR MENSAJE -->
          <h2 v-if="status">{{ mensaje }}</h2>
        </v-row>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      mensaje: "¡ Aqui estoy !",
      status
    };
  }
};
</script>

<style>
</style>