<template>
  <div class="app">
    <p>{{name}}- {{age}}</p>
    <button @click="changeName('Zelda')">change the name</button>
    <button @click="changeAge('99')">change the age</button>
    <p>{{ nameWithRef }}</p>
    <p>{{ ageWithRef }}</p>
  </div>
  
</template>

<script lang="ts">
import { defineComponent, reactive, toRefs, ref } from 'vue';

export default defineComponent({ // defineComponent for typescript component
  name: 'App',
  components: { },
  setup(){
    const state = reactive({
      name: 'Link',
      age: 256 as number | string // as or reactive object
    })

    const nameWithRef = ref('John')
    const ageWithRef = ref<number | string>(40) // <type> for ref

    ageWithRef.value = '33'

    return {...toRefs(state), nameWithRef, ageWithRef} 
  },

  methods: {
    changeName(newName: string){
      this.name = newName
      return newName
    },
    changeAge(newAge: string | number ){
      this.age = newAge
    }
  }
});
</script>

<style>


</style>
