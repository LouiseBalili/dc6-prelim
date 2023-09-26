<script setup>
import { inject } from 'vue';

const accent = inject('accent')
defineProps({
    client: Object
})
</script>

<template>
    <div class="card border border-solid border-2 border-gray-600 mt-5 mx-auto" style="width: 18rem;">
      <div class="card-body py-2 px-5 relative">
        <h5 class="card-title">{{ client.first_name }} {{ client.last_name }}</h5>
        <h6 class="card-subtitle mb-2 text-muted">level: {{ client.level }}</h6>
        <p class="card-text">{{ client.address }}</p>
        <p class="card-text">{{ client.phone }}</p>
        <button type="button"
        :class="{
            'bg-gray-900' : accent == '',
            'bg-blue-600' : accent == 'Blue',
            'bg-red-600' : accent == 'Red',
            'bg-green-600' : accent == 'Green',
        }"
        class="px-4 py-1.5 rounded-md text-sm text-white bottom-0 left-0">click me</button>
      </div>
    </div>
  </template>


