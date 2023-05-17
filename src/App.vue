<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <nav>
      <RouterLink to="/">Home</RouterLink>
      <RouterLink to="/aufgabe1">Aufgabe 1</RouterLink>
      <RouterLink to="/aufgabe2">Aufgabe 2</RouterLink>
      <RouterLink to="/aufgabe12_2">Aufgabe 12.2</RouterLink>
      <RouterLink to="/rwd">RWD</RouterLink>
      <RouterLink to="/dialogform">Dialogform</RouterLink>
      <RouterLink to="/kasse">Kasse</RouterLink>
    </nav>
  </header>

  <RouterView />
</template>

<style scoped>
nav {
  display: flex;
  justify-content: center;
  padding: 20px 0px;
  background-color: aqua;
}

nav a {
  display: block;
  color: black;
  text-decoration: none;
  margin: 0 10px;
  font-size: 1.5rem;
}
nav a:hover {
  color: green;
}
</style>
