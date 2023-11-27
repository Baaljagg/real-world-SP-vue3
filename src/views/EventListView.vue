<script setup>
import EventCard from '../components/EventCard.vue'
import { ref } from 'vue'

const events = ref ([
  {
  id: 5928101,
  category: "animal welfare",
  title: "Cat Adoption Day",
  description: "Find your ner feline friend at this event.",
  location: "Mewow Town",
  date: "January 28, 2024",
  time: "12:00",
  petsAllowed: true,
  organizer: "Kat Laydee",
},
{
  id: 4428101,
  category: "animal welfare 2",
  title: "Cat Adoption Day 2",
  description: "Find your ner feline friend at this event.",
  location: "Mewow Town",
  date: "May 5, 2024",
  time: "12:00",
  petsAllowed: true,
  organizer: "Kat Laydee 2",
},
{
  id: 2255101,
  category: "animal welfare 3",
  title: "Cat Adoption Day 3",
  description: "Find your ner feline friend at this event.",
  location: "Mewow Town",
  date: "August 14, 2024",
  time: "12:00",
  petsAllowed: true,
  organizer: "Kat Laydee 3",
},

])
</script>

<template>
  <h1>Events for good</h1>
  <div class="events">
   <EventCard v-for="event in events" :key="event.id" :event="event"/>
  </div>
</template>

<style scooped>
.events {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
