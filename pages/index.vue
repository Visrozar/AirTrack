<template>
  <section class="container">
    <div>
      <h1>Air Shipment Tracker</h1>
      <h2>Track Air shipments using AWB number</h2>
      <h1 v-if="error">here is the error {{ error }}</h1>
      <TrackShipment @awb-number="trackShipment" />
    </div>
  </section>
</template>

<script>
import TrackShipment from '~/components/TrackShipment.vue'
import axios from 'axios'

export default {
  components: {
    TrackShipment
  },
  data() {
    return {
      error: null,
      data: null
    }
  },
  methods: {
    async trackShipment(awbNumber) {
      const config = {
        headers: {
          Accept: 'application/json'
        }
      }

      try {
        const res = await axios.post(
          'http://devairtrack.freightbro.com/track',
          {
            awb_number: awbNumber
          },
          config
        )
        console.log(res.data)
      } catch (error) {
        this.error = error.response.data.message
        console.log(error.response)
      }
    }
  },
  head() {
    return {
      title: 'Air Shipment Tracker',
      meta: [
        {
          hid: 'title',
          name: 'title',
          content: 'Air shipments tracker'
        },
        {
          hid: 'description',
          name: 'description',
          content: 'Track Air shipments using AWB number'
        }
      ]
    }
  }
}
</script>

<style></style>
