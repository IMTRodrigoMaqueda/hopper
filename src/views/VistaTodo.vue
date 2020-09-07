<template>
  <v-conteiner>
    <v-row>
      <v-col>
        <v-card outlined>
          <Primero />
        </v-card>
        <v-card outlined>
          <Tercero />
        </v-card>
      </v-col>
      <v-col align-self="center">
        <v-card outlined>
          <Segundo />
        </v-card>
      </v-col>
    </v-row>
  </v-conteiner>
</template>

<script>
// @ is an alias to /src
import Primero from "@/components/Primero.vue";
import Segundo from "@/components/Segundo.vue";
import Tercero from "@/components/Tercero.vue";

export default {
  components: {
    Primero,
    Segundo,
    Tercero
  }
};
</script>
