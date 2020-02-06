<template>
    <div>
        <h1>Lista de Eventos :]</h1>
        <EventCard v-for="event in events" :key="event.id" :event="event"/>
    </div>
</template>

<script>
import EventCard from '@/components/EventCard.vue'
import axios from 'axios'

export default {
    components: {
        EventCard
    },
    data() {
        return {
            events: []
        }
    },
    created() {
        axios
            .get('http://localhost:3000/events')
            .then(response => {
                this.events = response.data
            })
            .catch(error => {
                console.log('Problema com:', error.response)
            })
    }
}
</script>

<style scoped></style>
