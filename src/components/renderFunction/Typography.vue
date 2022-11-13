<script setup>
import { h, useSlots } from 'vue';

const classNames = {
  '1': 'text-5xl',
  '2': 'text-4xl',
  '3': 'text-3xl',
  '4': 'text-2xl',
  '5': 'text-xl',
  '6': 'text-lg',
}

const props = defineProps({
  level: {
    type: String,
    default: '1',
    validator(value) {
      const intValue = parseInt(value);
      return intValue > 0 && intValue < 7;
    }
  }
})

const slots = useSlots();

const tag = 'h' + props.level;
const className = classNames[props.level] || 'text-lg';

const vnode = () => h(tag, { class: className }, slots);
</script>

<template>
  <div>
    <vnode />
  </div>
</template>
