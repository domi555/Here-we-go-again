<template>
  <v-app>
    <LogoBar></LogoBar>
    <CarCards :cars="cars" @refresh="loadCars"></CarCards>
  </v-app>
</template>

<script>
import LogoBar from '@/components/LogoBar.vue';
import CarCards from '@/components/CarCards.vue';
import axios from 'axios';

export default {
  name: 'App',
  components: {
    LogoBar,
    CarCards,
  },
  async created() {
    await this.loadCars();
  },
  data: () => ({
    cars: null,
  }),
  methods: {
    async loadCars() {
      try {
        const result = await axios({
          url: 'http://localhost:3000/cars',
          method: 'get',
        });
        this.cars = result.data;
      } catch {
        console.error('Error');
      }
    },
  },
};
</script>
