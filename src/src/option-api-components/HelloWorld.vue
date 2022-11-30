<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h1>{{ book.title }}/{{ book.author }}/{{ book.year }}</h1>
    <h1>{{ msg2 }}</h1>
    <h1>{{ fullName }} {{ this.user.age }}</h1>
  </div>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue';

interface Book {
  title: string,
  author: string,
  year: number
}

export interface User {
  firstName: string;
  lastName: string;
  age: number;
}

export default defineComponent({
  name: 'HelloWorld',
  props: {
    msg2:String,
    user: {
      type: Object as PropType<User>,
      required: true
    }
  },
  data() {
    return {
      msg: 'Hello TypeScript' as string,
      book: {
        title: 'Vue 3 Guide',
        author: 'Vue Team',
        year: 2020
      } as Book
    }
  },
  computed:{
    getLength(): number {
      return this.msg.length
    },
    fullName(): string {
      return this.user.firstName + ' ' + this.user.lastName
    }
  },
  methods: {
    changeMsg() {
      this.msg = 'Hello World';
    },
    changeYear(){
      this.book.year = 2021
    }
  },
});
</script>
