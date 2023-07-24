<script setup>
import { ref } from 'vue'
const refIndex = ref(1)

const toggleButton = (n) => {
   
    if (refIndex.value === n) {
        refIndex.value = 0
    } else {
        refIndex.value = n
    }
}

</script>

<template>
  <section class="container mx-auto flex items-center flex-col">
        <h1 class="text-center text-2xl py-10">Assignment</h1>
        <p class="p-5">Make These Buttons Work</p>
        <div class="flex justify-between space-x-6">
            <div class="p-10 border w-96 flex flex-col space-y-5">
                <button @click="toggleButton(n)" v-for="(n,index) in 3" :key="n" class="text-white font-bold py-2 px-4 rounded" :class="refIndex==n ?'bg-blue-500 hover:bg-blue-700':'bg-gray-500 hover:bg-gray-700' ">
                    Light {{ n }} On
                </button>
            </div>
            <div class="p-10 border w-96 flex flex-col space-y-5">
                <img v-for="n in 3" class="w-20" :src="refIndex==n?'//img.icons8.com/?size=512&id=12244&format=png':'//img.icons8.com/?size=512&id=75&format=png'" :alt="refIndex==n?'light_on':'light_off'">
            </div>
        </div>
    </section>
</template>

<style scoped></style>