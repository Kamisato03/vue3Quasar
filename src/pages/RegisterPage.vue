<template>
  <form-user @usuarios="userRegistro" :type="tipo"></form-user>
  <ul>
    <li v-for="(value, propiedad) in newUser" :key="propiedad">
      {{ propiedad }}: {{ value }}
    </li>
  </ul>
</template>

<script setup>
import { reactive } from "vue";
import FormUser from "../components/FormUser.vue";
const newUser = reactive({});
const tipo = "registro";

const userRegistro = (user) => {
  Object.assign(newUser, user);
};
</script>
