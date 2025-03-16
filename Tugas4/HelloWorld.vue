<script setup>
import { ref } from "vue";

const count = ref(100);
const inputText = ref("");

const IsColor = ref(false);
const isAwesome = ref(true);

function increment() {
  count.value++;
}

function decrement() {
  count.value--;
}

function changeColor() {
  IsColor.value = IsColor.value;
}

function Awesome() {
  isAwesome.value = !isAwesome.value;
}
</script>

<template>
  <h1>Count: {{ count }}</h1>

  <input v-model="inputText" placeholder="Masukan text" />
  <p>Text yang diMasukan:{{ inputText }}</p>

  <button @click="increment">Tambah</button>
  <button @click="decrement">Kurang</button>

  <h1 :class="IsColorr ? 'color1' : 'color2'">Red or Blue</h1>
  <button @click="changeColor">change color</button>

  <button @click="Awesome">toggle</button>
  <h1 v-if="isAwesome">Nice Day</h1>
  <h1 v-else>Bad day</h1>
</template>

<style>
.color1 {
  color: red;
}

.color2 {
  color: blue;
}
</style>
