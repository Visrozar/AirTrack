<template>
  <div>
    <v-card class="mb-4 mt-4">
      <v-container class="grey lighten-4" fluid grid-list-md>
        <v-layout row wrap>
          <v-flex md2>
            <div class="pb-2 subheading grey--text">
              {{ data.airline_details.name }}
            </div>
            <div class="caption font-style">AWB NO: {{ data.awb_number }}</div>
          </v-flex>
          <v-flex>
            <!-- <v-icon>flight_takeoff</v-icon> -->
            <div class="pb-2 subheading grey--text">Origin</div>
            <div class="caption font-style">
              <span>{{ data.origin.name }}</span>
            </div>
          </v-flex>
          <v-flex>
            <!-- <v-icon>flight_land</v-icon> -->
            <div class="pb-2 subheading grey--text">Destination</div>
            <div class="caption font-style">
              <span>{{ data.destination.name }}</span>
            </div>
          </v-flex>
          <v-flex>
            <div class="pb-2 subheading grey--text">Pieces</div>
            <div class="caption font-style">
              {{ data.shipment_details.pieces }}
            </div>
          </v-flex>

          <v-flex>
            <div class="pb-2 subheading grey--text">Actual Weight</div>
            <div class="caption font-style">
              {{ data.shipment_details.weight }}
            </div>
          </v-flex>

          <v-flex>
            <div class="pb-2 subheading grey--text">Status</div>
            <div class="caption font-style font-weight-bold text-uppercase">
              {{ data.current_status.name }}
            </div>
          </v-flex>
        </v-layout>
      </v-container>
    </v-card>
  </div>
</template>

<script>
export default {
  name: 'ShipmentDetails',
  props: ['data'],
  data() {
    return {
      awbNumber: ''
    }
  },
  methods: {
    onSubmit() {
      this.$emit('awb-number', this.awbNumber)
      this.awbNumber = ''
    }
  }
}
</script>

<style></style>
