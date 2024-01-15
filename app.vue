<script lang="ts" setup>
  import { SpeedInsights } from "@vercel/speed-insights/nuxt"
</script>

<template>
  <SpeedInsights/>
  <div class="max-w-3xl px-4 mx-auto">
    <header class="mt-8 mb-4 flex justify-between content-center">     
      <div class="flex justify-between">
        <div class="mr-4">
          <UAvatar
            size="xl"
            src="/img/default.png"
            alt="Avatar"
          />
        </div>
        <div>
          <h1 class="text-2xl font-semibold">
            <ULink to="/">AH WIRAYUDHA</ULink>
          </h1>
          <p class="text-gray-500">It's Personal</p>
        </div>
      </div>
      <ULink to="/bookmark" :key="Date.now()">
        <UButton>Bookmark History</UButton>
      </ULink>     
    </header>
    <NuxtPage />
    <footer class="mt-8 mb-4 flex justify-end content-center">
      © 2024 Ah Wirayudha. All rights reserved.
    </footer>
  </div>
</template>