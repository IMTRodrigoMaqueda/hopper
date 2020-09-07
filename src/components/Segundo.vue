<template>
  <v-conteiner>
    <!-- TITULO -->
    <h1 align="center">Listas</h1>
    <v-row align="center" justify="space-around">
      <v-card>
        <v-toolbar color="black" dark>
          <!-- INPUT -->
          <v-text-field
            v-model="item"
            label="Inserta Texto"
            hint="Este texto se agregará a la Lista"
            persistent-hint
            solo
            dense
          ></v-text-field>

          <v-spacer></v-spacer>

          <!-- BOTON AGREGAR -->
          <v-btn icon @click="agregar()">
            <v-icon>mdi-plus</v-icon>
          </v-btn>

          <!-- BOTON ELIMINAR TODA LA LISTA -->
          <v-btn v-if="lista.length>0" @click="reset()">
            <v-icon left color="red">mdi-eraser</v-icon>Eliminar todo
          </v-btn>
        </v-toolbar>

        <v-list>
          <v-list-item-group v-model="item" color="primary">
            <v-list-item v-for="elemento in lista" v-bind:key="elemento">
              <v-list-item-content>
                <v-list-item-title v-text="elemento"></v-list-item-title>
                <v-divider></v-divider>
              </v-list-item-content>
            </v-list-item>
          </v-list-item-group>
        </v-list>
      </v-card>
    </v-row>
  </v-conteiner>
</template>

<script>
export default {
  data() {
    return {
      lista: [],
      item: ""
    };
  },
  methods: {
    agregar() {
      this.lista.push(this.item), (this.item = "");
    },
    reset() {
      this.lista.splice(0, this.lista.length);
    }
  }
};
</script>

<style>
</style>