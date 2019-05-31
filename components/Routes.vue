<template>
  <div>
    <v-card class="mb-4 mt-4">
      <v-container class="grey lighten-4" grid-list-lg>
        <Route
          v-for="(route, index) in data.routes"
          :key="index"
          :route="route"
        />
      </v-container>
    </v-card>
  </div>
</template>

<script>
import Route from '~/components/Route.vue'

export default {
  name: 'Routes',
  props: ['data'],
  components: {
    Route
  }
}
</script>

<style></style>
