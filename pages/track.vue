<template>
  <section class="container">
    <div>
      <shipment />
    </div>
  </section>
</template>

<script>
export default {
  components: {},
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
