<script lang="ts" setup>
useHead({
  title: "My Own Bookmark History",
});
</script>

<template>
  <main>
    <ContentList 
      path="/home/bookmark"
      fields="title,date,thumbnail"
      :query="{
        draft: false,
        sort: [
          {
            date: -1,
          },
        ],
      }"
      v-slot="{ list }"
      :key="Date.now()"
    >
      <div v-for="item in list" v-bind:key="item.title" class="mb-4">
        <UContainer>
          <UCard>
            <figure class="md:flex bg-slate-100 rounded-xl p-8 md:p-0 dark:bg-slate-800">
              <img 
                class="w-24 h-24 md:w-48 md:h-auto rounded-l-lg" 
                v-if="item.thumbnail"
                :src="item.thumbnail"
                :alt="item.title"
                width="384" 
                height="512"
              />
              <div class="pt-6 md:p-8 text-center md:text-left space-y-4">
                <blockquote>
                  <p class="text-lg font-medium">
                    {{ item.title }}
                  </p>
                </blockquote>
                <figcaption class="font-medium space-y-2">
                  <div class="text-sky-500 dark:text-sky-400">
                    {{ item.date }}
                  </div>
                  <div class="text-slate-700 dark:text-slate-500">
                    <UButton>more</UButton>
                  </div>
                </figcaption>
              </div>              
            </figure>
          </UCard>
        </UContainer>
      </div>
    </ContentList>
  </main>
</template>