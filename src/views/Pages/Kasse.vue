<script setup>
import { ref } from "vue";

const log = ref([
    {
        id: 1,
        text: 'Startsaldo',
        value: 1500
    },
    {
        id: 2,
        text: 'Bus-Abo',
        value: -79
    },
        {
        id: 3,
        text: 'Handy-Abo',
        value: -35
    }
])

const currentId = ref(2)

function roundTo05(number){
    return (Math.ceil(number*20)/20).toFixed(2);
}

const newText = ref();
const newValue = ref();

function addEntry(){
    const newElement = {
        text: newText.value,
        value: parseFloat(newValue.value),
        id: ++currentId.value
    }

    log.value.push(newElement);

    newText.value = '';
    newValue.value = '';
}

function deleteLog(id) { 
    //log.value = log.value.filter(entry => entry.id !== id);

    log.value = log.value.filter((element)=>{
        return element.id !== id
    })

 }

</script>

<template>
<table>
    <thead>
        <tr>
            <th>Text</th>
            <th>Eingang</th>
            <th>Ausgang</th>
        </tr>
    </thead>
    <tbody>
        <tr v-for="logEntry in log" :key="logEntry.id" :class="logEntry.value > 0 ? 'text-green' : 'text-red'">
            <td>{{logEntry.text}}</td>
            <td><span v-if="logEntry.value > 0">{{roundTo05(logEntry.value)}} CHF</span></td>
            <td><span v-if="logEntry.value < 0">{{roundTo05(logEntry.value)}} CHF</span></td>
            <td><button @click="deleteLog(logEntry.id)">Eintrag löschen</button></td>
        </tr>
    </tbody>
</table>

<div class="wrapper">
    <h2>Neuer Eintrag erfassen</h2>
    <div class="form">
        <div class="form-row">
            <label for="text">Text</label>
            <input type="text" id="text" name="text" v-model="newText" @keyup.enter="addEntry">
        </div>

        <div class="form-row">
            <label for="amount">Betrag</label>
            <input type="number" id="amount" name="amount" v-model="newValue" @keyup.enter="addEntry">
        </div>

        <div class="form-row">
            <button @click="addEntry">Speichern</button>
        </div>


    </div>
</div>


</template>

<style lang="scss">

table{
    width: 500px;
    margin: 0 auto;
    margin-top: 50px;
}


.wrapper{
    width: 500px;
    margin: 0 auto; 
}

.form{
    .form-row{
        display: flex;
        margin-bottom: 10px;

        label{
            width:30%;
        }

    }
}


table,
th,
td {
    border-collapse: collapse;
    padding: 1rem;
    text-align: left;
}

thead th {
    position: sticky;
    top: 0;
    left: 0;
    background-color: #d5d1defe;
    cursor: pointer;
    text-transform: capitalize;
}

tbody tr:nth-child(even) {
    background-color: #0000000b;
}

tbody tr {
    --delay: .1s;
    transition: .5s ease-in-out var(--delay), background-color 0s;
}

tbody tr.hide {
    opacity: 0;
    transform: translateX(100%);
}

tbody tr:hover {
    background-color: #fff6 !important;
}

tbody tr td,
tbody tr td p,
tbody tr td img {
    transition: .2s ease-in-out;
}

tbody tr.hide td,
tbody tr.hide td p {
    padding: 0;
    font: 0 / 0 sans-serif;
    transition: .2s ease-in-out .5s;
}

</style>