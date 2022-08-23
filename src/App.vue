<template>
  <ChatComp />
</template>

<script>
import ChatComp from './components/ChatComp.vue'

export default {
  name: 'App',
  components: {
    ChatComp,
  }
}
</script>
<style>
@import url('https://fonts.googleapis.com/css2?family=Ubuntu:wght@300&display=swap');

body {
  background-color: #00a000;
  font-family: Ubuntu;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: flex;
  flex-direction: column-reverse;
  width: 95vw;
  height: 80vh;

}
</style>
