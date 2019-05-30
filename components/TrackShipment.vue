<template>
  <form @submit.prevent="onSubmit">
    <input v-model="awbNumber" type="text" placeholder="AWB number" />
    <input type="submit" value="Track Shipment" />
  </form>
</template>

<script>
export default {
  name: 'TrackShipment',
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
