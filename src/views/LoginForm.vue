<script setup>
import LoginAside from '../components/v-model/LoginAside.vue';
import PasswordInput from '../components/v-model/PasswordInput.vue';
import { ref } from 'vue';

const email = ref("");
const password = ref("");


function login() {
  console.log(password.value);
}

</script>

<template>
  <div class="flex min-h-screen">
    <div class="w-1/2 flex items-center justify-center">
      <form class="w-2/3" @submit.prevent="login">
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
      </form>
    </div>
    <login-aside />
  </div>
</template>
