<template>
  <v-card max-width="300">
    <v-img height="250" :src="car.image"></v-img>
    <v-card-title>{{ car.title }}</v-card-title>
    <v-card-text>
      <div class="mb-2">
        Owner:
        <span class="font-weight-bold">{{
          `${car.owner.firstName} ${car.owner.lastName}`
        }}</span>
      </div>
      <div>
        Year: <span class="font-weight-bold">{{ car.yearOfMake }}</span>
      </div>
      <div class="mb-2">
        Miles: <span class="font-weight-bold">{{ car.miles }}</span>
      </div>
      <div class="mb-2">
        Price: <span class="font-weight-bold">{{ car.price }}</span>
      </div>
      <div class="mb-3">
        {{ car.description }}
      </div>
      <v-btn class="red darken-3 white--text" @click="$emit('reserve', car)"
        >Buy car</v-btn
      >
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  props: {
    car: {
      type: Object,
    },
  },
};
</script>
