<template>
  <v-container grid-list-xs>
    <v-card v-for="restaurant in restaurants" :key="restaurant.name">
      <v-card-title primary-title>
        {{ restaurant.name }}
      </v-card-title>
      <v-card-text>
        {{ restaurant.description }}
      </v-card-text>
      <v-card-text>
        <v-chip v-for="category in restaurant.categories" :key="category.name" color="primary" class="mx-3">
          {{ category.name }}
        </v-chip>
      </v-card-text>
    </v-card>
  </v-container>
</template>

<script>
export default {
  data () {
    return {
      restaurants: []
    }
  },
  async fetch () {
    this.restaurants = await await this.$axios.$get('http://localhost:1337/restaurants')
  }
}
</script>

<style lang="scss" scoped>

</style>
