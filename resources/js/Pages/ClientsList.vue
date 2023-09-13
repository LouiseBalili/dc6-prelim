<script setup>
    import SideLayout from '@/Layouts/SideLayout.vue'
    import ClientCard from '@/Components/c.vue';
</script>

<template>

<SideLayout>
    <div class="p-8" style="padding: 12px; background-color: #c0ccd6">
        <h1 class="text-4xl text-gray-700 my-6">Clients List</h1>
    </div>

    <div class="container">
        <client-card :client="$page.props.client" />
    </div>

</SideLayout>

</template>
