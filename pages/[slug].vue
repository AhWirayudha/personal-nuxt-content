<script lang="ts" setup>
const { slug } = useRoute().params;
const formatDate = (date: any) => {
  if (!date) return '';
  return new Date(date).toLocaleDateString('en-US');
}
</script>

<template>
  <article class="rounded-2xl">
    <ContentDoc :path="`/home/bookmark/${slug}`" v-slot="{ doc }">
      <!-- Header  -->
      <header>
        <div class="text-center p-5">
          <h1 class="text-4xl font-bold lg:w-2/3 mx-auto">{{ doc.title }}</h1>
          <p class="text-gray-500 text-sm mt-2">{{ formatDate(doc.date) }}</p>
        </div>
        <div class="h-auto">
          <img
            v-if="doc.thumbnail"
            :src="doc.thumbnail"
            :alt="doc.title"
            width="200px"
            class="mx-auto"
          />
        </div>
      </header>
      <!-- ./ Header  -->

      <!-- Content -->
      <div class="mt-4 content p-5">
        <!-- Content  -->
        <ContentRenderer :value="doc" />
        <!-- ./ Content  -->
      </div>
      <!-- ./ Content  -->
    </ContentDoc>
  </article>
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