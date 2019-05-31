<template>
  <div>
    <v-layout row wrap class="padding-bottom-15">
      <v-flex md4>
        <v-icon color="red lighten-2">flight_takeoff</v-icon>
        <span class="caption font-style">{{ route.origin.name }}</span>
      </v-flex>
      <v-flex md4>
        <v-icon color="red lighten-2">flight_land</v-icon>
        <span class="caption font-style">{{ route.origin.name }}</span>
      </v-flex>
      <v-flex md4>
        <v-icon color="red lighten-2">location_on</v-icon>
        <span class="subheading font-style font-weight-bold text-uppercase">
          {{ route.current_status.name }}
        </span>
      </v-flex>
    </v-layout>
    <v-divider></v-divider>
  </div>
</template>

<script>
export default {
  name: 'Route',
  props: ['route']
}
</script>

<style></style>
