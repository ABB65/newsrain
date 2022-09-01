<script lang="ts" setup>
const { data: news } = await useFetch('https://baconipsum.com/api/?type=meat-and-filler')
</script>

<template>
  <div class="app w-full min-h-screen bg-neutral-100 dark:bg-neutral-900">
    <div class="container mx-auto px-4 py-4">
      <NewsHeader />
      <div class="content w-full flex flex-wrap gap-8 py-16">
        <NewsCard
          v-for="(element,i) in news"
          :key="i"
          :order="i"
          :featured="i%3===0"
          :title="element.split(' ', Math.floor(Math.random() * 20) + 1).join(' ')"
          :description="element"
        />
        <NewsCard
          v-for="(element,i) in news"
          :key="i + 'k'"
          :order="i"
          :featured="i%3 ===0"
          :title="element.split(' ', Math.floor(Math.random() * 20) + 1).join(' ')"
          :description="element"
        />
        <NewsCard
          v-for="(element,i) in news"
          :key="i + 'z'"
          :order="i"
          :featured="i%3 ===0"
          :title="element.split(' ', Math.floor(Math.random() * 20) + 1).join(' ')"
          :description="element"
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
