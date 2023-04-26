<template>
    <Header :message="msg" @new-message="updateMessage"> </Header>    
    <button @click="changeMessage"> Alterar mensagem</button>
</template>
<script setup>
import { ref } from "vue";
import Header from "./components/Header.vue";

const msg = ref("teste");

function changeMessage(){
  msg.value = "Mensagem do pai !"
}

function updateMessage(newMessage){
  msg.value = newMessage;
}

</script>
<style></style>
