<script setup>
import { ref, onMounted } from 'vue'
import EventService from '@/services/EventService.js'

const props = defineProps({
  id: {
    required: true,
  }
})

const event  = ref(null)

onMounted(() => {
    // fetch event by id and set local date
    EventService.getEvent(props.id)
    .then((response) => {
      event.value = response.data
    })
    .catch((error) => {
      console.log(error)
    })
})
</script>

<template>
  <div v-if="event">
    <h1>{{ event.title }}</h1>
    <nav>
      <RouterLink
      :to="{ name: 'event-details' }">
      Details</RouterLink> | 

      <RouterLink
      :to="{ name: 'event-register' }">
      Register</RouterLink> | 

      <RouterLink
      :to="{ name: 'event-edit' }">
      Edit</RouterLink>
    </nav>
    <RouterView :event="event" />
  </div>
</template>