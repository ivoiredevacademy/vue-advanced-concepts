<script setup>
import Tabs from '../components/inject-provide/Tabs.vue';
import Tab from '../components/inject-provide/Tab.vue';
</script>

<template>
  <div class="p-10">
    <Tabs>
      <Tab title="First tab" id="1" active>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. Aliquid facere at vero id sint quod, nulla laudantium eos consectetur ratione reiciendis tempora incidunt cupiditate, distinctio repellendus quo excepturi, in porro.
        </p>
      </Tab>
      <Tab title="Second tab" id="2">
        <h1 class="text-2xl">My tab</h1>
        <p>
          Lorem, ipsum dolor sit amet consectetur adipisicing elit. Quo delectus repellendus voluptate, velit veritatis voluptatum molestias architecto quidem modi odio recusandae? Expedita aliquam saepe repudiandae eaque quibusdam numquam aperiam cupiditate.
        </p>
      </Tab>
    </Tabs>
  </div>
</template>
