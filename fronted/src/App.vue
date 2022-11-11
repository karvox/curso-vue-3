<template>

<div>

  {{ count }}
  {{ userName }}

  <ul>
    <li v-for="user in users">{{ user.firstName }} - {{ user.age }}</li>
  </ul>
  <button v-on:click="count++">Add one</button>

  <h2>App</h2>

  <router-link to="/">Home</router-link>
  <router-link to="/about">About</router-link>
  <router-view></router-view>

</div>

</template>


<script setup>

import {onMounted, onUnmounted, onUpdated, reactive, ref} from "vue";

const count = ref(0);
const userName = ref('Alexandre');

const users = reactive([
  {
    firstName:'Alexandre',
    age:40
  },
  {
    firstName:'Maria',
    age:45
  }
])

onMounted(() => {
  console.log();
})

onUnmounted(() => {
  console.log('unmounted');
})

onUpdated(() => {
  console.log('updated');
})

</script>


<style scoped>

</style>