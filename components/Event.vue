<template>
  <v-timeline-item :color="color">
    <!-- <template v-slot:opposite> -->
    <!-- <span>{{
      new Date(
        event.event_details.event_date + ' ' + event.event_details.event_time
      )
    }}</span> -->
    <!-- </template> -->
    <v-card class="elevation-2 grey lighten-4">
      <v-card-title class="title">
        <div>{{ event.event_details.status.name }}</div>
      </v-card-title>

      <v-card-text>
        <div class="body-2">
          Flight Number: {{ event.flight_details.flight_number }}
        </div>
        <div class="body-2">
          {{
            new Date(
              event.event_details.event_date +
                ' ' +
                event.event_details.event_time
            )
          }}
        </div>
      </v-card-text>
    </v-card>
  </v-timeline-item>
</template>

<script>
export default {
  name: 'Event',
  props: ['event', 'id'],
  data() {
    return {
      color: this.id === 0 ? 'green lighten-2' : 'red lighten-2'
    }
  }
}
</script>

<style>
.red {
  background-color: #f44336;
}
.green {
  background-color: #81c784;
}
</style>
