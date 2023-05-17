<template>


<button :class="dialog">Open</button>

<dialog  @click="dialog">
    <form method="dialog">
    <input type="text" />
    <button class="close-dialog" type="submit">Submit</button>
  </form>
</dialog>

<form>
<h5>Username</h5>
    <input type="text" id="username" name="username">

    <h5>Vorname</h5>
    <input type="text" id="firstname" name="firstname">

    <h5>Nachname</h5>
    <input type="text" id="lastname" name="lastname">

    <h5>Email</h5>
    <input type="email" id="email" name="email">

    <h5>Strasse</h5>
    <input type="text" id="street" name="street">

    <h5>PLZ</h5>
    <input type="text" id="zip-code" name="zip-code">

    <h5>Passwort</h5>
    <input type="password" id="password" name="password">

    <select>
    <option value="1">1.Lehrjahr</option>
    <option value="2">2.Lehrjahr</option>
    <option value="3">3.Lehrjahr</option>
    </select>

</form>
    
  
</template>

<script setup>
import { ref } from 'vue';

  const dialog = ref('');

</script>

<style>

form{
    display: flex;
    flex-direction: column;

}

h5 {
    color: #434242;
    text-transform: uppercase;
    font-size: 10px;
    letter-spacing: 1px;

}

input[type="text"],
input[type="email"],
input[type="password"],
select{
    width: 300px;
    border: 0;
    background: transparent;
    border-bottom: 1px solid #3fb6a8;
    padding: 7px 0;
    font-size: 15px;
    text-transform: none;
    outline: none;
}

</style>