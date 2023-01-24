<script setup lang = "ts">
const user = useSupabaseUser()
</script>

<template>
  <div class="w-1/10 h-screen fixed left-0 top-0 bg-gray-800">
    <div class="flex flex-col h-full justify-items-center justify-center">
      <NuxtLink to="/">
        <button class="px-2 py-1 text-white bg-gray-700 mb-2">
          <span class="self-center text-l font-semibold text-white">
            <Icon class="text-xl" name="mdi:home" />
          </span>
        </button>
      </NuxtLink>
      <template v-if="!user">
        <NuxtLink to="/login">
          <button class="px-2 py-1 text-white bg-gray-700 mb-2">
            <span class="self-center text-l font-semibold text-white">
              <Icon class="text-xl" name="mdi:user" />
            </span>
          </button>
        </NuxtLink>
        <!-- <NuxtLink to="/register">
          <button class="px-2 py-1 text-white bg-gray-700 mb-2">
            <span class="self-center text-l font-semibold text-white">Register</span>
          </button>
        </NuxtLink> -->
        <NuxtLink to="/MagicLink">
          <button class="px-2 py-1 text-white bg-gray-700 mb-2">
            <span class="self-center text-l font-semibold text-white">
              <Icon class="text-xl" name="mdi:email-send" />
            </span>
          </button>
        </NuxtLink>
        </template>
        <button class="px-2 py-1 text-white bg-gray-700 mb-2" v-else>
          <NuxtLink to="/protected">
            <span class="self-center text-l font-semibold text-white">
              <Icon class="text-xl" name="mdi:lock" />
            </span>
          </NuxtLink>
        </button>



    </div>
  </div>

  <!-- <nav class="bg-white border-gray-200 px-2 sm:px-4 py-2.5 dark:bg-gray-900">
    <div class="container flex flex-wrap items-center justify-between mx-auto">
      <a>
        <span class="self-center text-xl font-semibold whitespace-nowrap dark:text-white">Podcast Wundercomm</span>
      </a>
      <ul class="flex">
        <li class="mr-6">
          <NuxtLink to="/">
            <span class="self-center text-l font-semibold text-white">Home</span>
          </NuxtLink>
        </li>
        <template v-if="!user">
          <li class="mr-6">
            <NuxtLink to="/login">
            <span class="self-center text-l font-semibold text-white">Login</span>
            </NuxtLink>
          </li>
          <li class="mr-6">
            <NuxtLink to="/register">
              <span class="self-center text-l font-semibold text-white">Register</span>
            </NuxtLink>
          </li>
          <li class="mr-6">
            <NuxtLink to="/magiclink">
              <span class="self-center text-l font-semibold text-white">MagicLink</span>
            </NuxtLink>
          </li>
        </template>
        <li v-else>
          <NuxtLink to="/protected">
            <span class="self-center text-l font-semibold text-white">Protected</span>
          </NuxtLink>
        </li>
      </ul>
    </div>
  </nav> -->
  <NuxtPage/>
</template>
