<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <p>{{ msg }}</p>
  <HelloWorld :msg2="msg2" />
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import HelloWorld, { User } from './components/HelloWorld.vue';

interface State {
  msg: string;
}

export default defineComponent({
  name: 'App',
  components: {
    HelloWorld
  },
  setup() {
    const msg = ref<string>('Hello TypeScript By App.vue')
    const msg2 = ref<string>("Welcome to Your Vue.js + TypeScript App By CompositionApi")

    //   person: {
    //     firstName: 'John',
    //     lastName: 'doe',
    //     age: 30
    //   } as User
    // }

    return {
      msg,
      msg2
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
