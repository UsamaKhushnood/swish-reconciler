<template>
  <div
    class="bg-cyan-950 h-full flex md:block flex-col justify-center p-6 md:p-10 hover:shadow-lg shadow-md transition-all group relative text-primary-foreground"
  >
    <h1 class="text-xl font-bold">Invoicing</h1>
    <p class="mt-3">
      Lorem, ipsum dolor sit amet consectetur adipisicing elit. Mollitia aut
      consectetur quae necessitatibus placeat adipisci facilis accusantium eum
      facere ducimus quidem ullam, reprehenderit cupiditate et dolor nostrum,
      quasi, ipsum commodi iste voluptatum architecto quod consequuntur? Dolore
      numquam
    </p>
    <button class="mt-3 flex gap-1 items-center font-bold">
      Learn more
      <Icon
        icon="radix-icons:chevron-right"
        class="h-[1.2rem] w-[1.2rem]"
      ></Icon>
    </button>
  </div>
</template>
<script setup>
import { Icon } from "@iconify/vue";
</script>
