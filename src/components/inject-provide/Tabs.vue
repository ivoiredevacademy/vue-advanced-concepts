<script setup>
import { provide } from 'vue';

provide('tabsTitle', []);

</script>

<template>
  <div>

    <slot></slot>
  </div>
</template>
