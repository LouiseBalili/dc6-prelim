<script setup>
    import MainNav from '@/Components/MainNav.vue'
    import { ref, provide } from 'vue';

    let width = ref('w-[250px]')
    let hidden = ref("")

    function toggleWidth() {
        if(width.value == 'w-[250px]') {
            width.value = 'w-[300px]';
            hidden.value = "hidden";
        }else {
            width.value = ['w-[250px]']
            hidden.value = ""
        }
    }

    const accent = ref('')

    function setColorToBlue() {
        accent.value = 'Blue';
    }
    function setColorToRed() {
        accent.value = 'Red';
    }
    function setColorToGreen() {
        accent.value = 'Green';
    }
    function setColorToGray() {
        accent.value = '';
    }

    provide('accent', accent)
</script>

<template>

<div class="flex min-h-screen">
    <div id="sidebar"
    :class="{
            'bg-gray-900' : accent == '',
            'bg-blue-600' : accent == 'Blue',
            'bg-red-600' : accent == 'Red',
            'bg-green-600' : accent == 'Green',
            width
        }"
    class="p-6 duration-500" style="position: relative;">
        <button class="text-xl text-gray-600" @click="toggleWidth" style="position: absolute; right: 10px; top:10px">
            <i class="fa-solid fa-bars"></i>
        </button>
        <div id="branding" :class="hidden">
            <img src="https://64.media.tumblr.com/a3c917f8dcbecbbf7ee7c820f0291352/c2df127863837518-5e/s500x750/5971fc9d9d7fafc424f23b4aedcf2ff104fdb2d4.jpg" alt="Louise Balili"
                class="w-[170px] h-[170px] mx-auto rounded-full object-cover">
            <h1 class="text-3xl text-center text-gray-200 my-6"></h1>

        </div>
        <hr class="border-gray-600">

        <MainNav></MainNav>

        <div class="mt-10">
            <div class="flex justify-center items-center">
                <button
                @click="setColorToBlue()"
                type="button"
                class="rounded-l-md px-4 py-1.5 bg-blue-600 text-sm text-white w-[70px]">Blue</button>
                <button
                @click="setColorToRed()"
                type="button"
                class="px-4 py-1.5 bg-red-600 text-sm text-white w-[70px]">Red</button>
                <button
                @click="setColorToGreen()"
                type="button"
                class="px-4 py-1.5 bg-green-600 text-sm text-white w-[70px]">Green</button>
                <button
                @click="setColorToGray()"
                type="button"
                class="rounded-r-md px-4 py-1.5 bg-gray-900 text-sm text-white w-[70px]">Gray</button>
            </div>
        </div>
    </div>
    <div id="container" class="flex-1">
        <slot />
    </div>

</div>

</template>
