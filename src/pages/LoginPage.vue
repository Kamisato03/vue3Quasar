<template>
  <form-user @usuarios="userLogin" :type="tipo"></form-user>
  <ul>
    <li v-for="(value, propiedad) in newUser" :key="propiedad">
      {{ propiedad }}: {{ value }}
    </li>
  </ul>
  {{ newUser.email }}
</template>

<script setup>
import { reactive } from "vue";
import FormUser from "../components/FormUser.vue";
const newUser = reactive({});
const tipo = "login";

const userLogin = (user) => {
  Object.assign(newUser, user);
};
</script>
