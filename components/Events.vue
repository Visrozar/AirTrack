<template>
  <v-timeline align-top dense>
    <Event
      v-for="(event, index) in data.events.reverse()"
      :key="index"
      :id="index"
      :event="event"
    />
  </v-timeline>
</template>

<script>
import Event from '~/components/Event.vue'

export default {
  name: 'Events',
  props: ['data'],
  components: {
    Event
  }
}
</script>

<style></style>
