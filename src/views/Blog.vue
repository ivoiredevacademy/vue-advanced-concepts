<script setup>
import { ref } from 'vue';
import BlogCard from '../components/slot/Card.vue';

const post = ref({
    id: 1,
    title: "What's new in Vue 3 ?",
    description: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolore minus rerum, reiciendis consectetur neque recusandae, soluta minima nemo nulla quisquam natus corporis debitis excepturi, consequuntur voluptates reprehenderit voluptate iusto culpa!",
    createdAt: "10-09-2022",
    cover: 'https://cdn.cdnlogo.com/logos/v/92/vue-js.svg'
})

</script>
    
<template>
    <div class="flex min-h-screen bg-blue-100">
        <div class="w-full flex items-center justify-center">
            <blog-card :post="post" />
        </div>
    </div>
</template>