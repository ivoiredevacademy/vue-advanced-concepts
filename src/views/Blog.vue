<script setup>
import { ref } from 'vue';
import BlogCard from '../components/slot/Card.vue';
import BlogCardSlot from '../components/slot/CardSlot.vue';

const post = ref({
  id: 1,
  title: "What's new in Vue 3 ?",
  description: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolore minus rerum, reiciendis consectetur neque recusandae, soluta minima nemo nulla quisquam natus corporis debitis excepturi, consequuntur voluptates reprehenderit voluptate iusto culpa!",
  createdAt: "10-09-2022",
  cover: 'https://cdn.cdnlogo.com/logos/v/92/vue-js.svg'
})

</script>

<template>
  <div class="flex flex-col min-h-screen bg-blue-200 py-20">
    <div class="flex items-center justify-center">
      <blog-card :post="post" />
    </div>
    <div class="flex items-center justify-center">
      <blog-card-slot :cover="post.cover">
        <div>
          <h1 class="text-3xl font-semibold">{{ post.title }}</h1>
          <p>{{ post.description }}</p>
        </div>
        <template  v-slot:footer>
          <span class="">
            {{ post.createdAt }}
          </span>
        </template>
      </blog-card-slot>
    </div>
  </div>
</template>
