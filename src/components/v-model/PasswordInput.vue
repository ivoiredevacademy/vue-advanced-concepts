<script setup>
import { ref, computed, defineProps, defineEmits } from 'vue';

const canSee = ref(false);
const emits = defineEmits(['update:password'])
const inputType = computed(() => canSee.value ? 'text' : 'password');
const iconClassName = computed(() => canSee.value ? 'lar la-eye-slash' : 'lar la-eye');
const props = defineProps({
  password: {
    type: String,
    required: true,
    default: ""
  }
})

function toggle() {
  canSee.value = !canSee.value;
}
</script>

<template>
  <div class="password-input-container">
    <input :type="inputType" class="form-input" placeholder="*********" :value="props.password"
      @input="emits('update:password', $event.target.value)">
    <a href="#" class="eye-container" @click.prevent="toggle"><i :class="iconClassName"></i></a>
  </div>
</template>