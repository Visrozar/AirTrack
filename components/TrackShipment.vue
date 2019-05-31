<template>
  <v-form @submit.prevent="onSubmit">
    <v-container>
      <v-layout row justify-center>
        <v-flex sm4>
          <div>
            <v-text-field
              v-model="awbNumber"
              :error-messages="error"
              label="AWB number"
              prepend-icon="airplanemode_active"
              :loading="loading"
              outline
              required
            ></v-text-field>
          </div>
          <div>
            <v-btn type="submit" color="red lighten-2">Track Shipment</v-btn>
          </div>
        </v-flex>
      </v-layout>
    </v-container>
  </v-form>
</template>

<script>
export default {
  name: 'TrackShipment',
  props: ['error', 'loading'],
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
