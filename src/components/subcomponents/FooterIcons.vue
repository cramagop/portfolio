<script setup>
   import IconLinkedin from '../icons/IconLinkedin.vue'
   import IconGit from '../icons/IconGit.vue';
</script>

<template>
   <div class="footer__icons">
      <IconLinkedin />
      <IconGit />
   </div>
</template>

<style>
   .footer__icons {
      display: flex;
      flex-direction: row;
      flex-wrap: wrap;
      justify-content: center;
      margin-top: 10px;
   }
    .footer__icon {
        width: 50px;
        height: 50px;
        margin: 10px;
    }
    .footer__icon img {
    width: 100%;
    height: 100%;
    }

    .footer__icon img:hover {
        opacity: 0.5;
    }
</style>