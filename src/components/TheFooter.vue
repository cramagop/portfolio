<script setup>
   import FooterIcons from './subcomponents/FooterIcons.vue';
   import FooterLastUpdate from './subcomponents/FooterLastUpdate.vue'
</script>

<template>
   <div class="footer">
      <FooterIcons />
      <FooterLastUpdate />
   </div>
</template>

<style scoped>
   .footer {
      display: flex;
      flex-direction: column;
      flex-wrap: wrap;
      align-content: center;
   }
</style>