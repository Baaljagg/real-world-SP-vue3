<script setup>
import { useRouter } from 'vue-router';
import { inject } from 'vue';

const { event } = defineProps(["event"]);
const router = useRouter()

const GStore = inject('GStore')

const register = () => {
    //if registration API call is sucćessful
    GStore.flashmessage = 'You are successfuly registered for ' + event.title
    setTimeout(() => {
        GStore.flashmessage = ''
    }, 3000)
    //push back to the event details
    router.push({
        name: 'event-details',
    })

}

</script>

<template>
    <p>Register for the event here</p>
    <button @click="register">Register me!</button>
</template>