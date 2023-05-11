<template>
  <q-btn color="primary" :label="tittle" @click="sumarBien()" />
</template>

<script setup>
import { ref, defineProps } from "vue";
const conter = ref(0);

const emit = defineEmits(["sumarContador"]);
defineProps({
  tittle: String,
});

const sumarBien = () => {
  conter.value++;
  emit("sumarContador", conter);
};
</script>
