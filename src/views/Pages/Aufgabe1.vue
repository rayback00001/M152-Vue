<template>

  <div class="main">
    <h1>Color Switcher</h1>
    <button :class="bgColor + ' ' + textColor">{{ textColor }} auf {{ bgColor }}</button>

    <ul>
      <h4>Background Color</h4>
        <li @click="bgColor = 'bg-red'">Red</li>
        <li @click="bgColor = 'bg-green'">Green</li>
        <li @click="bgColor = 'bg-yellow'">Yellow</li>
        <li @click="bgColor = 'bg-blue'">Blue</li>
    </ul>

    <ul>
      <h4>Text Color</h4>
        <li @click="textColor = 'text-red'">Red</li>
        <li @click="textColor = 'text-green'">Green</li>
        <li @click="textColor = 'text-yellow'">Yellow</li>
        <li @click="textColor = 'text-blue'">Blue</li>
    </ul>


  </div>
  
</template>

<script setup>
import { ref } from 'vue';


  const bgColor = ref('');
  const textColor = ref('');

</script>

<style>

*{
  list-style: none;
}

.text-red{color: red;}

.text-green{color: green;}

.text-yellow{color: yellow;}

.text-blue{color: blue;}

.bg-red{background-color: red;}

.bg-green{background-color: green;}

.bg-yellow{background-color: yellow;}

.bg-blue{background-color: blue;}

.main{
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
}

ul li{
  text-align: center;
}


</style>