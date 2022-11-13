<script setup>
import { h, useAttrs, useSlots } from 'vue';

const slots = useSlots();
const attrs = useAttrs();

const sizeClassNames = {
  'sm': 'px-2 py-1 text-sm',
  'lg': 'px-4 py-2 text-lg',
  'xl': 'px-8 py-4'
}

const typeClassNames = {
  primary: 'bg-blue-500 text-white',
  danger: 'bg-red-500 text-white'
};


const props = defineProps({
  tag: {
    default: 'button',
    validator(value) {
      return ['a', 'button'].includes(value);
    }
  },
  size: {
    default: 'lg',
    validator(value) {
      return ['sm', 'lg', 'xl'].includes(value);
    }
  },
  type: {
    default: 'primary',
    validator(value) {
      return ['primary', 'danger'].includes(value);
    }
  },
  loading: {
    type: Boolean,
    default: false
  }
})

const newAttrs = {
  onClick: attrs.onPress
}

let className = sizeClassNames[props.size] || sizeClassNames['lg'];
className += ' cursor-pointer rounded-lg m-1 ' + typeClassNames[props.type] || typeClassNames['primary'];


const render = () => h(props.tag, { class: className, ...newAttrs }, props.loading ? 'Loading...' : slots);
</script>

<template>
  <render />
</template>
