<template>
  <div class="app">
      <JobList :jobs="jobs" />
  </div>
  
</template>

<script lang="ts">
import { defineComponent, reactive, toRefs, ref } from 'vue';
import Job from './types/Job'
import JobList from './components/JobList.vue'

export default defineComponent({ // defineComponent for typescript component
  name: 'App',
  components: { JobList },
  setup(){
    const jobs = ref<Job[]>([
      {
        title: 'farm worker',
        location: 'Lon Lon Ranch',
        salary: 30000,
        id: '1'
      },
      {
        title: 'quary man',
        location: 'Death Mountain',
        salary: 32000,
        id: '2'
      },
      {
        title: 'flute player',
        location: 'The lost Wood',
        salary: 40000,
        id: '3'
      },
      {
        title: 'fisherman',
        location: 'Lake Hylia',
        salary: 30000,
        id: '4'
      },
      {
        title: 'prison guard',
        location: 'Gerudo Valley',
        salary: 25000,
        id: '5'
      },
    ])

    return { jobs }
  },


});
</script>

<style>


</style>
