<template>
  <div class="todo">
    <Primero /> -----------------------------------------------------------------------------------------------------------------------------
    <Segundo /> -----------------------------------------------------------------------------------------------------------------------------
    <Tercero /> -----------------------------------------------------------------------------------------------------------------------------
  </div>
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
    Tercero,
  }
};
</script>
