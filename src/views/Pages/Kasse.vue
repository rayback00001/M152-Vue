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
            <td class="text-left">{{logEntry.text}}</td>
            <td class="text-right"><span v-if="logEntry.value > 0">{{roundTo05(logEntry.value)}} CHF</span></td>
            <td class="text-right"><span v-if="logEntry.value < 0">{{roundTo05(logEntry.value)}} CHF</span></td>
        </tr>
    </tbody>
</table>

</template>

<style lang="scss">

table{
    width: 500px;
    margin: 0 auto;
}

tr th{
     border-bottom: 2px solid darkgray;
}

tr td{
    border-bottom: 1px solid grey;
}


.text-right{
    text-align: right;
}

.text-left{
    text-align: left;
}
</style>