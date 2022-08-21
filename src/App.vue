<template>
  <ChatComp />
</template>

<script>
import ChatComp from './components/chatComp.vue'

export default {
  name: 'App',
  components: {
    ChatComp,
  }
}
</script>

<style>
body {
  background-color: #00a000;
  font-family: Ubuntu;
  color: #2c3e50;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: flex;
  flex-direction: column-reverse;
  width: 90vw;
  height: 90vh;

}
</style>
