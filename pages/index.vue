<template>
  <section class="container">
    <div>
      <div class="text-xs-center">
        <h1 class="display-3">Air Shipment Tracker</h1>
        <h2 class="subheading">Track Air shipments using AWB number</h2>
        <TrackShipment
          :error="error"
          :loading="loading"
          @awb-number="trackShipment"
        />
      </div>

      <v-divider></v-divider>
      <Shipment v-if="data" :key="data._id" :data="data" />
      <v-divider></v-divider>
      <Routes v-if="data" :key="data._id" :data="data" />
      <v-divider></v-divider>
      <Events v-if="data" :key="data._id" :data="data" />
    </div>
  </section>
</template>

<script>
import TrackShipment from '~/components/TrackShipment.vue'
import Shipment from '~/components/Shipment.vue'
import Routes from '~/components/Routes.vue'
import Events from '~/components/Events.vue'
import axios from 'axios'

export default {
  components: {
    TrackShipment,
    Shipment,
    Routes,
    Events
  },
  data() {
    return {
      error: null,
      data: null,
      loading: false
    }
  },
  methods: {
    async trackShipment(awbNumber) {
      this.loading = 'red lighten-2'
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
        this.data = res.data.data
        this.error = null
        this.loading = false
      } catch (error) {
        this.error = error.response.data.message
        this.data = null
        this.loading = false
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
