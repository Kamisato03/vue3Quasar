<template>
  <h3>usuarios</h3>
  <q-form @submit.prevent="registrarUsuario" ref="formAdd">
    <q-input
      v-model="email"
      label="Ingrese su correo"
      type="text"
      :rules="[
        (val) =>
          (val && /^[^@]+@[^@]+\.[a-zA-Z]{2,}$/.test(val)) ||
          'Formato incorrecto de email',
      ]"
      lazy-rules
    ></q-input>
    <q-input
      v-model="password"
      label="Ingrese su password"
      type="password"
      :rules="[
        (val) =>
          (val && val.length > 5) ||
          'El password debe tener mínimo 6 caracteres',
      ]"
      lazy-rules
    ></q-input>
    <q-input
      v-if="type === 'registro'"
      v-model="repassword"
      label="Repita su password"
      type="password"
      :rules="[
        (val) => (val && val === password) || 'Los passwords no coinciden',
      ]"
      lazy-rules
    ></q-input>
    <div>
      <q-btn :label="type" type="submit"></q-btn>
    </div>
  </q-form>
</template>

<script setup>
import { ref, reactive, defineProps } from "vue";
const email = ref("");
const password = ref("");
const repassword = ref("");
const formAdd = ref(null);

const user = reactive({
  email,
  password,
  repassword,
});

defineProps({
  type: String,
});

const emit = defineEmits(["usuarios"]);
const registrarUsuario = () => {
  emit("usuarios", user);
};
</script>
