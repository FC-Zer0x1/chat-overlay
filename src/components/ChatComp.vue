<template>
  <div>
    <div v-for="(item, index) in oldMessages" :key="index">
      <div class="oldMessage" v-if="oldMessages[index] != ''">
        <p>{{ oldMessages[index] }}</p>
        <span></span>
      </div>
    </div>
    <div class="newMessage">
      <div v-if="newMessage != ''">
        <p>{{ newMessage }}</p>
        <span></span>
      </div>
    </div>
    <input v-on:keyup.enter="appendMessage" id="nMessage" type="text" v-model="newMessage" />
  </div>
</template>

<script setup>
import { ref } from 'vue';

const newMessage = ref('');
const oldMessages = ref([]);
const appendMessage = () => {
  oldMessages.value.push(newMessage.value);
  newMessage.value = '';
  document.getElementById("nMessage").value = '';
}

</script>

<style scoped>
div {
  display: flex;
  flex-direction: column;
  margin: 2px 0px;
}

.newMessage {
  height: 1px;
}

.oldMessage {
  animation-duration: 10s;
  animation-name: ease-up;
  animation-fill-mode: forwards
}

@keyframes ease-up {
  0% {
    margin-bottom: -70px;
    opacity: 1;
  }

  10% {
    margin-bottom: 0px;
  }

  90% {
    margin-bottom: 0px;
    opacity: 1;
  }

  100% {
    margin-bottom: 8px;
    opacity: 0;
  }
}

p {
  display: inline-block;
  margin: 0vw 2vw;
  padding: 1rem 0.8rem;
  background: #F2F4FA;
  color: black;
  border-radius: 12px;
  width: fit-content;
  max-width: 90%;
  word-wrap: break-word;
  font-weight: 300;
  font-size: 2vh;
  bottom: 0;
}

span {
  content: '';
  z-index: -10;
  margin-top: -10px;
  margin-left: 2vw;
  height: 1.125rem;
  width: 0.875rem;
  background: #F2F4FA;
  border-bottom-right-radius: 20px;
}

input {
  top: 0;
  left: 0;
  color: rgba(0, 0, 0, 0);
  background-color: rgba(0, 0, 0, 0);
  outline: none;
  border: none;
  position: absolute;
  width: 99%;
  height: 99%;
}
</style>
