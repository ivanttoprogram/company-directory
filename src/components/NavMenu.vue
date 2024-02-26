<template>
  <nav class="bg-slate-800 h-20 items-center text-white flex justify-center space-x-6">
    <RouterLink :to="{name: 'Home'}">Home</RouterLink>
    <RouterLink :to="{name: 'Other'}">Other</RouterLink>
  
    <RouterLink :to="{name: 'SettingsPage'}">Settings</RouterLink>

    <div v-if="isAuthenticated">
    Welcome {{  user.email }}
    <button @click="logout" class="rounded-md bg-red-600 px-4 py-2 mx-4 text-red-200 hover:bg-red-800">LOGOUT</button>
    </div>
    <div v-else>
        <RouterLink :to="{name: 'LoginPage'}">Login</RouterLink>
    </div>
  </nav>
</template>

<!--<style lang="postcss" scoped>
nav {
  @apply flex justify-center space-x-4;

  & .router-link-active {
    @apply underline underline-offset-4;
  }
}
</style> -->

<script setup>
import { useAuth } from '../composables/useAuth'
const { isAuthenticated, logout, user } = useAuth()

</script>