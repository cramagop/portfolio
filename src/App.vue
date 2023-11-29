<script setup>
import { RouterLink, RouterView } from 'vue-router'
import TheFooter from './views/FooterView.vue'
import TheHeader from './views/HeaderView.vue'

</script>

<template>
    <TheHeader />
    
    <RouterView />

    <TheFooter />
</template>