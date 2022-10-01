<script lang="ts" setup>

const { pending, data: news } = await useLazyFetch('https://newsapi.org/v2/everything?q=bitcoin&apiKey=f844884cc4844867b03ff2bca1d12dce')
console.log(news.value, pending)
watch(news, (newNews) => {
  console.log(newNews)
  // Because posts starts out null, you won't have access
  // to its contents immediately, but you can watch it.
})
</script>

<template>
  <div class="app w-full min-h-screen bg-neutral-100 dark:bg-neutral-900">
    <div class="container mx-auto px-4 py-4">
      <NewsHeader />
      <div class="content w-full flex flex-wrap gap-16 py-16">
        <NewsCard
          v-for="(element,i) in news.articles"
          :key="i"
          :order="i"
          :featured="i%3===0"
          :title="element?.title"
          :description="element?.description"
          :content="element?.content"
          :image="element.urlToImage"
        />
      </div>
    </div>
  </div>
</template>

<style lang="postcss">

@import url('https://fonts.googleapis.com/css2?family=Edu+VIC+WA+NT+Beginner:wght@400;500;600;700&family=Raleway:wght@400;500;600;700&display=swap');

html {
  font-family: 'Raleway', sans-serif;
  /* font-size: 18px; */
}
.logo-text {
  font-family: "Edu VIC WA NT Beginner", cursive;
}
.default-text {
  @apply text-neutral-900 dark:text-neutral-100;
}
h1,h2,h3,h4,h5,h6 {
  @apply default-text font-semibold;

}
h1 {
  @apply text-4xl;
}

h2 {
  @apply text-3xl;
}

h3 {
  @apply text-2xl;
}

h4 {
  @apply text-xl;
}

h5 {
  @apply text-lg;
}
p {
  @apply default-text;
}

</style>
