<script lang="ts" setup>
useHead({
  link: [
    {
      href: 'https://cdn.jsdelivr.net/npm/remixicon@2.5.0/fonts/remixicon.css',
      rel: 'stylesheet'
    }
  ]
})

const colorMode = useColorMode()
const changeMode = () =>
  colorMode.value === 'light'
    ? (colorMode.preference = 'dark')
    : (colorMode.preference = 'light')
</script>
<template>
  <header class="w-full flex items-center justify-between">
    <div class="logo-container flex items-center">
      <span class="inline-block">
        <svg id="logo-72" class="w-10 h-auto" viewBox="0 0 53 44" fill="#DC2626" xmlns="http://www.w3.org/2000/svg">
          <path
            d="M23.2997 0L52.0461 28.6301V44H38.6311V34.1553L17.7522 13.3607L13.415 13.3607L13.415 44H0L0 0L23.2997 0ZM38.6311 15.2694V0L52.0461 0V15.2694L38.6311 15.2694Z"
            class="newsrain-logo-icon"
            fill="#DC2626"
          />
        </svg>
      </span>
      <span class="logo-text text-3xl font-bold default-text ml-4 hidden lg:inline">Newsrain</span>
    </div>
    <form class="w-full max-w-sm pl-8 lg:pl-0">
      <div class="flex items-center border-b border-red-500 py-2">
        <input
          class="appearance-none bg-transparent border-none w-full mr-3 py-1 px-2 leading-tight focus:outline-none bg-neutral-100
        dark:bg-neutral-900
        text-neutral-900
        dark:text-neutral-100
              "
          type="email"
          placeholder="subscribe@mymail.com"
          aria-label="My Email"
        >
        <button
          class="
        px-3
        py-1
        bg-neutral-900
        dark:bg-neutral-100
        text-neutral-100
        dark:text-neutral-900
        font-semibold
      "
        >
          Subscribe
        </button>
      </div>
      <div class="mobile-social-links pt-4 w-full flex items-center justify-between lg:hidden">
        <button class="mx-1 p-1" @click="changeMode()">
          <i
            :class="$colorMode.value !== 'light' ? 'ri-sun-fill' : 'ri-moon-fill'"
            class="text-2xl text-red-500"
          />
        </button>
        <a class="mx-1 p-1" href="http://" target="_blank" rel="noopener noreferrer"> <i
          class="text-2xl default-text ri-github-fill"
        /></a>
        <a class="mx-1 p-1" href="http://" target="_blank" rel="noopener noreferrer"> <i
          class="text-2xl default-text ri-twitter-fill"
        /></a>
        <a class="mx-1 p-1" href="http://" target="_blank" rel="noopener noreferrer"> <i
          class="text-2xl default-text ri-linkedin-fill"
        /></a>
        <a class="mx-1 p-1" href="http://" target="_blank" rel="noopener noreferrer"> <i
          class="text-2xl default-text ri-discord-fill"
        /></a>
      </div>
    </form>
    <div class="social-links hidden lg:block">
      <button class="mx-1 p-1" @click="changeMode()">
        <i
          :class="$colorMode.value !== 'light' ? 'ri-sun-fill' : 'ri-moon-fill'"
          class="text-2xl text-red-500"
        />
      </button>
      <a class="mx-1 p-1" href="http://" target="_blank" rel="noopener noreferrer"> <i
        class="text-2xl default-text ri-github-fill"
      /></a>
      <a class="mx-1 p-1" href="http://" target="_blank" rel="noopener noreferrer"> <i
        class="text-2xl default-text ri-twitter-fill"
      /></a>
      <a class="mx-1 p-1" href="http://" target="_blank" rel="noopener noreferrer"> <i
        class="text-2xl default-text ri-linkedin-fill"
      /></a>
      <a class="mx-1 p-1" href="http://" target="_blank" rel="noopener noreferrer"> <i
        class="text-2xl default-text ri-discord-fill"
      /></a>
    </div>
  </header>
</template>
