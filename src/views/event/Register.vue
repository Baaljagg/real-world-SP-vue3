<script setup>
import { useRouter } from 'vue-router';
const props = defineProps(["event"]);
const router = useRouter()

const register = () => {
    //if registration API call is sucćessful
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