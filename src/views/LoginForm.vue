<script setup>
import LoginAside from '../components/LoginAside.vue';
import PasswordInput from '../components/subviews/PasswordInput.vue';
import { ref } from 'vue';

const email = ref('');
const password = ref("");

</script>

<template>
  <div class="flex min-h-screen">
    <div class="w-1/2 flex items-center justify-center">
      <div class="w-2/3">
        <h2 class="text-4xl font-semibold">Connexion</h2>
        <div class="form-group">
          <label for="#">Email</label>
          <input type="text" class="form-input" placeholder="Ex: john@example.com"
            v-model="email"
          >
        </div>
        <div class="form-group">
          <label for="#">Password</label>
          <password-input v-model:password="password"/>
        </div>
        <div>
          <button class="btn">Se connecter</button>
        </div>
      </div>
    </div>
    <login-aside />
  </div>
</template>