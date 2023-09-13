<script>
export default {
  props: {
    client: Object,
  },
};
</script>

<template>
    <div class="card" style="width: 18rem;">
      <div class="card-body">
        <h5 class="card-title">{{ client.first_name }} {{ client.last_name }}</h5>
        <h6 class="card-subtitle mb-2 text-muted">level: {{ client.level }}</h6>
        <p class="card-text">{{ client.address }}</p>
        <p class="card-text">{{ client.phone }}</p>
      </div>
    </div>
  </template>


