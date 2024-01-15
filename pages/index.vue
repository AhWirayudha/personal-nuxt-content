<script lang="ts" setup>
useHead({
  title: "It's Personal",
});
</script>

<template>
  <main>
    <ContentDoc :path="`/home/me`" v-slot="{ doc }">
      <article>
        <div class="mt-4 content mb-4">
          <ContentRenderer :value="doc" />
        </div>
      </article>
    </ContentDoc>
  </main>
</template>

<style>
.content p:not(:last-child),
.content li:not(:last-child),
.content blockquote:not(:last-child),
.content h1:not(:last-child),
.content h2:not(:last-child),
.content h3:not(:last-child),
.content h4:not(:last-child),
.content pre:not(:last-child),
.content table:not(:last-child) {
  @apply mb-4;
}

.content h1 {
  @apply text-3xl font-bold;
}
.content h2 {
  @apply text-2xl font-bold;
}
.content h3 {
  @apply text-xl font-bold;
}
.content h4 {
  @apply text-lg font-bold;
}
.content h5 {
  @apply text-base font-bold;
}
</style>