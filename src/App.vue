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
  if(counter.value >= 0){
    counter.value--;
  }
}

// Define a function to reset the counter value
function reset(){
  counter.value = counter_init_value;
}

</script>

<template>
  <div class="counter-value">
    {{ counter }}
  </div>
  <div class="counter-actions">
    <button class="increment-action" @click="increment">Increment</button>
    <button class="decrement-action" @click="decrement">Decrement</button>
    <button class="reset-action" @click="reset">Reset</button>

  </div>
  
</template>

<style scoped></style>
