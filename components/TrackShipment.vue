<template>
  <v-form @submit.prevent="onSubmit">
    <v-container>
      <v-layout>
        <v-flex xs12 md4>
          <v-text-field
            v-model="awbNumber"
            :error-messages="error"
            label="AWB number"
            prepend-icon="airplanemode_active"
            color="red lighten-2"
            outline
            required
          ></v-text-field>
        </v-flex>
        <v-flex xs12 md4>
          <v-btn type="submit" color="red lighten-2">Track Shipment</v-btn>
        </v-flex>
      </v-layout>
    </v-container>
  </v-form>
</template>

<script>
export default {
  name: 'TrackShipment',
  props: ['error'],
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
