<template>
  <div>
    <button-conter :contador="contador" @sumarContador="sumRes"></button-conter>
    <h1>{{ contador }}</h1>

    <h1>------------------</h1>
  </div>
</template>

<script setup>
import { ref } from "vue";
import ButtonConter from "../components/ButtonConter.vue";

const contador = ref(0);
const active = false;
const name = "Gabo";
const fruta = {
  name: "manzana",
  price: "$5",
};
const colors = ["blue", "red", "green"];
const arrayFrutas = [
  {
    name: "Manzana",
    price: "$1.00",
    description: "Una manzana",
    stock: 0,
  },
  {
    name: "Pera",
    price: "$2.00",
    description: "Una pera",
    stock: 10,
  },
  {
    name: "Naranja",
    price: "$3.00",
    description: "Una naranja",
    stock: 20,
  },
];

const sumRes = (conter) => {
  contador.value = conter;
};
</script>
