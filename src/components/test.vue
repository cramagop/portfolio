<script setup>
    defineProps ({
      content : Object
    });
</script>

<template>
      <ul>
        <template v-for="(item, key) in content">
          <li v-if="'isLink' in item">{{ key }} : <a :href="item.link">{{ item.link }}</a></li>
          <li v-else>{{ key }} : {{ item }}</li>
        </template>
      </ul>
</template>