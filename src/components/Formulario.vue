<template>
  <v-container>
    <v-row align="center" justify="space-around">
      <h1>Formulario</h1>
    </v-row>

    <v-col>
      <v-form ref="form" v-model="valid">
        <!-- INPUT NOMBRE -->
        <v-row>
          <v-text-field v-model="nombre" label="Nombre" :rules="nombreReglas"></v-text-field>
        </v-row>

        <!-- INPUT CORREO -->
        <v-row>
          <v-text-field v-model="correo" label="Correo" :rules="correoReglas"></v-text-field>
        </v-row>

        <!-- INPUT NIVEL -->
        <v-row>
          <v-slider
            v-model="nivel"
            label="Nivel de Satisfaccion"
            :rules="nivelReglas"
            max="5"
            :thumb-size="24"
            thumb-label="always"
          ></v-slider>
        </v-row>

        <!-- BOTON ENVIAR -->
        <v-row align="center" justify="space-around">
          <v-btn v-model="send" :disabled="!valid" @click="buildJSON()" text color="primary">
            Enviar
            <v-icon dark right>mdi-send</v-icon>
          </v-btn>
        </v-row>
      </v-form>
    </v-col>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      json: "",
      valid: true,
      send: null,
      nombre: "",
      correo: "",
      nivel: 5,
      nombreReglas: [
        value => !!value || "Nombre Requerido.",
        value => (value && value.length >= 4) || "Mínimo 4 caracteres"
      ],
      correoReglas: [
        value => !!value || "Correo Requerido.",
        value => /\S+@\S+.\S+/.test(value) || "Correo inválido"
      ],
      nivelReglas: [
        value => !!value || "No puedes tener nivel 0 de satisfacción"
      ]
    };
  },
  methods: {
    validar() {
      this.$refs.form.validate();
    },
    buildJSON() {
      this.json = {
        nombre: this.nombre,
        correo: this.correo,
        nivel: this.nivel
      };
      console.log(JSON.stringify(this.json));
      return this.json;
    }
  }
};
</script>

<style>
</style>