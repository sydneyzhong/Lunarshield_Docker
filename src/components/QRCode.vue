<template>
  <v-card class="mx-auto" max-width="300">
    <v-card-title>{{ title }}</v-card-title>
    <v-card-text class="text-center">
      <img :src="qrImage" :alt="title" class="qr-code" />
    </v-card-text>
  </v-card>
</template>

<script setup>
defineProps({
  title: {
    type: String,
    required: true
  },
  qrImage: {
    type: String,
    required: true
  }
})
</script>

<style scoped>
.qr-code {
  max-width: 200px;
  width: 100%;
  height: auto;
}
</style>