<template>
  <div class="app">
    <p>{{name}}- {{age}}</p>
    <button @click="changeName('Zelda')">change the name</button>
    <button @click="changeAge(99)">change the age</button>
  </div>
  
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({ // defineComponent for typescript component
  name: 'App',
  components: { },
  data(){
    return {
      name: 'Link',
      age: 25 as number | string
    }
  },
  methods: {
    changeName(newName: string){
      this.name = newName
      return newName
    },
    changeAge(newAge: string | number){
      this.age = newAge
    }
  }
});
</script>

<style>


</style>
