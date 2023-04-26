<template>
  <div>
    <input type="text" v-model="newMessage" @keydown.enter="emitNewMessage">
    <p>{{ message }}</p>
  </div>
</template>

<script setup>
import { defineEmits, ref } from 'vue';
const  emit  = defineEmits(['new-message']);

const newMessage = ref('');

const emitNewMessage = () =>{
  console.log(newMessage.value);
  emit('new-message', newMessage.value.trim());
  newMessage.value = '';
}

const props = defineProps({
  message: String
});



</script>
