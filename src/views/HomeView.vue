<script setup>
    import TheHomeView from '../components/TheHomeView.vue'

    function underline(elementID) {
        document.getElementById(elementID).style.textDecoration = "underline";
    }

    function unUnderline(elementID) {
        document.getElementById(elementID).style.textDecoration = "none";
    }
</script>

<template>
    <TheHomeView @mouse-over="underline" @mouse-out="unUnderline"/>
</template>