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
p {
  display: inline-block;
  margin: 0px 10px;
  padding: 20px 10px;
  background: white;
  color: black;
  border-radius: 12px;
  width: fit-content;
  max-width: 90%;
  word-wrap: break-word;
  font-family: Ubuntu;
  font-weight: 300;
  /* font-size: 32px; */
  bottom: 0;
}

div {
  display: flex;
  flex-direction: column;
  margin: 2px 0px;

}

.newMessage {
  height: 30px;
}

.oldMessage {
  animation-duration: 10s;
  animation-name: ease-up;
  animation-fill-mode: forwards
}

@keyframes ease-up {
  0% {
    margin-bottom: -8px;
    opacity: 0;
  }

  10% {
    margin-bottom: 2px;
    opacity: 1;
  }

  90% {
    margin-bottom: 2px;
    opacity: 1;
  }

  100% {
    margin-bottom: 8px;
    opacity: 0;
  }
}

span {
  content: '';
  /* position: fixed; */
  z-index: -10;
  /* bottom: 0; */
  margin-top: -10px;
  margin-left: 10px;
  /* left: 18px; */
  height: 18px;
  width: 12px;
  background: white;
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
