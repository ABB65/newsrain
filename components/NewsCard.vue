<!-- eslint-disable @typescript-eslint/no-unused-vars -->
<script setup lang="ts">

const props = defineProps({
  title: { type: String, required: true },
  description: { type: String, required: true },
  featured: { type: Boolean }
})
const readingTime = () => {
  const text = props.description
  const wpm = 225
  const words = text.trim().split(/\s+/).length
  const time = Math.ceil(words / wpm)
  return time
}
</script>
<template>
  <div class="box-content news-card w-1/4 transition-all hover:grow-[12]" :class="featured ? 'grow-[8]': 'grow'">
    <div class="detail pl-4 clear-left h-80 overflow-hidden">
      <h2 class="border-b border-red-400 mb-4 h-[4.875rem] text-overflow overflow-hidden">
        {{ title }}
      </h2>
      <img
        class=" float-left w-1/2 mr-4"
        src="https://images.unsplash.com/photo-1633158829875-e5316a358c6f?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1170&q=80"
        alt=""
        srcset=""
      >
      <h5 class="inline text-ellipsis overflow-hidden">
        {{ description }}
      </h5>
    </div>
    <div class="menu w-full flex justify-between pl-4 pt-4">
      <div class="text-red-500">
        <i :class="featured ? 'inline-block' : 'hidden'" class="ri-flag-fill text-lg align-middle mr-1" />
        <span :class="featured ? 'inline-block' : 'hidden'" class="p-1">featured</span>
      </div>
      <div>
        <div class="flex items-center  text-neutral-500 p-1">
          <i class="ri-timer-fill text-lg align-middle mr-1" />
          {{ readingTime() }} min read
        </div>
      </div>
      <button
        class="
        read-more
        px-2
        py-1
        bg-neutral-900
        dark:bg-neutral-100
        text-neutral-500
        font-semibold
      "
      >
        Read More
      </button>
    </div>
  </div>
</template>

<style lang="postcss">

 .news-card {
  transition: all 200ms ease-in-out;
  &:hover {
    .read-more{
      @apply  text-neutral-100 dark:text-neutral-900;
    }
  }
}

</style>
