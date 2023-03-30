<template>
  <div class="app">
    <header>
      <div class="order">
        <button @click="updateSortCriteria('title')">order by title</button>
        <button @click="updateSortCriteria('salary')">order by salary</button>
        <button @click="updateSortCriteria('location')">order by location</button>
      </div>
    </header>
      <JobList :jobs="jobs" :sortCriteria="sortCriteria" />
  </div>
  
</template>

<script lang="ts">
import { defineComponent, reactive, toRefs, ref } from 'vue';
import Job from './types/Job'
import JobProperty from './types/JobProperty'
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

    const sortCriteria = ref<JobProperty>('title')

    const updateSortCriteria = (property: JobProperty) => {
      console.log(jobs.value)
      sortCriteria.value = property
      //jobs.value = jobs.value.sort((a,b)=>a[property] - b.property)
    }

    return { jobs, updateSortCriteria, sortCriteria }
  },


});
</script>

<style>

header {
  text-align: center;
}
header .order {
  margin-top: 20px;
}
button {
  margin: 0 10px;
  color: #1195c9;
  border: 3px solid #1195c9;
  background: #d5f0ff;
  padding: 8px 16px;
  border-radius: 4px;
  cursor: pointer;
  font-weight: bold;
}
</style>
