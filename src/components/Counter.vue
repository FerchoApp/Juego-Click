<script setup>
import { ref } from "vue";

let number = ref(0);
let time = ref(0);
let interval

function add() {
    if (number.value==0) {
        interval =setInterval(() => {
            time.value++
        }, 1000);
    }

    number.value++ 

    if(number.value == 100){
        clearInterval(interval)
    }
}
</script>

<template>
    
    <div @click="add" class="flex mt-80 items-center mx-auto justify-center bg-slate-600 text-white py-1 px-2 rounded w-20 h-20 text-center hover:cursor-pointer select-none ">
        {{ number }}
    </div>
    
    <div v-show="number > 0" class="flex mt-10 items-center mx-auto justify-center bg-slate-600 text-green-200 rounded py-1 px-2 w-20 text-center">
        Tiempo: {{ time }}
    </div>

    <div v-if="number==0" class="bg-slate-600  rounded text-white py-1 px-2 mx-auto w-40 mt-5 text-center">
        Dale click pe causa 🐱‍💻
    </div>
</template>
