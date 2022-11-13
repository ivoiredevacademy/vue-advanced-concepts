<script setup>
import VTypography from '../components/renderFunction/Typography.vue';
import VButton from '../components/renderFunction/Button.vue';
import VList from '../components/renderFunction/List.vue';


function showHello() {
  alert('Hello world')
}

</script>

<template>
  <div class="p-10">
    <h1 class="text-5xl text-center">Our design system</h1>
    <div class="py-10">
      <h1 class="text-4xl text-blue-800 font-semibold">Typography</h1>
      <hr class="mb-4">
      <v-typography level="1">
        Hello world
      </v-typography>
      <v-typography level="2">
        Hello world
      </v-typography>
      <v-typography level="3">
        Hello world
      </v-typography>
      <v-typography level="4">
        Hello world
      </v-typography>
      <v-typography level="5">
        Hello world
      </v-typography>
    </div>

    <div class="py-10">
      <h1 class="text-4xl text-blue-800 font-semibold ">Button</h1>
      <hr class="mb-4">
      <v-button size="lg" type="primary" tag="a">
        Hello world
      </v-button>
      <v-button size="lg" type="danger" :loading="true" @press="showHello">
        Hello world
      </v-button>
    </div>

    <div class="py-10">
      <h1 class="text-4xl text-blue-800 font-semibold ">Lists</h1>
      <hr class="mb-4">
      <v-list :items="['Juvenal', 'John', 'Peter']" />
    </div>
  </div>
</template>
