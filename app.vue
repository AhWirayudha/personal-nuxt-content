<template>
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
  </div>
</template>