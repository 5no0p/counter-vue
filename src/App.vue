<script setup>
import { ref } from 'vue'

// Define a defult value for the counter
const counter_init_value = 0;

// Define a reactive variable to hold the counter value
const counter = ref(counter_init_value)


// Define a function to increment the counter value
function increment(){
  counter.value++;
}

// Define a function to decrement the counter value
function decrement(){
  // Prevent the negative counter value by checking if the counter is grater than 0 befor decrement
  if(counter.value > 0){
    counter.value--;
  }
}

// Define a function to reset the counter value
function reset(){
  counter.value = counter_init_value;
}

</script>

<template>
  <section class="counter-container flex flex-col items-center justify-center min-h-screen">
    <h1 class="counter-title text-2xl font-bold mb-4">Counter App</h1>
  <div class="counter-value text-4xl font-bold text-center my-4">
    {{ counter }}
  </div>
  <div class="counter-actions flex gap-2 mx-auto">
    <button class="increment-action btn-primary" @click="increment">Increment</button>
    <button class="decrement-action btn-secondary" @click="decrement" :disabled="counter==0">Decrement</button>
    <button class="reset-action btn-ghost" @click="reset" :disabled="counter==0">Reset</button>

  </div>
  </section> 
</template>

<style scoped>
@reference "./assets/main.css";

.btn-primary {
  @apply px-4 py-2 bg-blue-600 text-white rounded;
}

.btn-secondary {
  @apply px-4 py-2 bg-gray-600 text-white rounded disabled:opacity-50 disabled:cursor-not-allowed;
}

.btn-ghost {
  @apply px-4 py-2 bg-transparent border border-gray-600 text-gray-600 rounded disabled:opacity-50 disabled:cursor-not-allowed;
}
</style>
