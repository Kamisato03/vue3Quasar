<template>
  <q-btn color="primary" label="sumar" @click="sumarBien()" />
</template>

<script setup>
import { ref } from "vue";
const conter = ref(0);

const emit = defineEmits(["sumarContador"]);

const sumarBien = () => {
  conter.value++;
  emit("sumarContador", conter);
};
</script>
