<template>
    <router-link class="event-link" :to="{ name: 'event-show', params: { id: '1' } }">
        <div class="event-card -shadow">
            <span class="eyebrown">@{{ evento.hora }} no {{ evento.data }}</span>
            <h4 class="title">{{ evento.titulo }}</h4>
            <span>{{ evento.presentes.length }} colantes</span>
        </div>
    </router-link>
</template>

<script>
export default {
    data() {
        return {
            evento: {
                id: 1,
                titulo: 'Marolar em Rivs',
                data: 'Sab, 8 Fev 2020',
                hora: '16:20',
                presentes: [
                    {id: 'qwe222', nome: 'brunao'},
                    {id: 'asd333', nome: 'ique'},
                ]
            }
        }
    },
}
</script>

<style scoped>
    .event-card {
      padding: 20px;
      margin-bottom: 24px;
      transition: all 0.2s linear;
      cursor: pointer;
    }
    .event-card:hover {
      transform: scale(1.01);
      box-shadow: 0 3px 12px 0 rgba(0, 0, 0, 0.2), 0 1px 15px 0 rgba(0, 0, 0, 0.19);
    }
    .event-card > .title {
      margin: 0;
    }
    
    .event-link {
      color: black;
      text-decoration: none;
      font-weight: 100;
    }
</style>