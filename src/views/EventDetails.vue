<script setup>
import { ref, onMounted } from 'vue';
import EventServices from '@/sevices/EventServices';

const event = ref(null)
const id = 123

onMounted(() => {
  EventServices.getEvent(id.value)
    .then((response) => {
      event.value = response.data
    })
    .catch((error) => {
      console.log(error)
    })
})

</script>

<template>
  <div>
    <h1>{{ event.title }}</h1>
    <p>{{ event.time }} on {{ event.date }} @ {{ event.location }}</p>
    <p>{{ event.description }}</p>
  </div>
</template>


<style lang="scss" scoped>

</style>
