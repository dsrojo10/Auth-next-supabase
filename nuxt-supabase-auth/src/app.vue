<script setup lang = "ts">
const user = useSupabaseUser()
</script>

<template>
  <div>
    <nav>
      <ul>
        <li>
          <NuxtLink to="/">Home</NuxtLink>
        </li>
        <template v-if="!user">
          <li>
            <NuxtLink to="/login">Login</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/register">Register</NuxtLink>
          </li>
        </template>
        <li v-else>
          <NuxtLink to="/protected">Protected</NuxtLink>
        </li>
      </ul>
    </nav>
    <NuxtPage/>
  </div>
</template>
