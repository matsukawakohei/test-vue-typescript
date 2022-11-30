<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg2="Welcome to Your Vue.js + TypeScript App" :user="user"/>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import HelloWorld, { User } from './components/HelloWorld.vue';

export default defineComponent({
  name: 'App',
  components: {
    HelloWorld
  },
  data() {
    return {
      person: {
        firstName: 'John',
        lastName: 'doe',
        age: 30
      } as User
    }
  },
  computed:{
    user(): User {
      return this.person;
    }
  }
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
