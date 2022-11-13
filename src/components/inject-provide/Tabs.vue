<script setup>
import { provide, ref } from 'vue';

const tabTitles = ref([]);
const activeTabId = ref(null);
provide('tabTitles', tabTitles);
provide('activeTabId', activeTabId);

function setActiveTab(tab) {
  activeTabId.value = tab.id;
}
</script>

<template>
  <div>
    <ul class="flex border-b border-b-gray-200">
      <li v-for="tab in tabTitles"
        class="mx-6 py-3 cursor-pointer border-b border-b-gray-200"
        :key="tab.id"
        @click="setActiveTab(tab)"
        :class="{'border-b-4 border-b-blue-500': activeTabId == tab.id}"
      >{{ tab.title }}</li>
    </ul>
    <slot></slot>
  </div>
</template>
