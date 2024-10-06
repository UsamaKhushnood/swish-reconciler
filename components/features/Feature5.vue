<template>
  <div
    class="bg-fuchsia-50 p-6 md:p-10 md:pb-0 overflow-hidden hover:shadow-lg shadow-md transition-all group h-full"
  >
    <h1 class="text-xl font-bold">Invoicing</h1>
    <p class="mt-3">
      Lorem, ipsum dolor sit amet consectetur adipisicing elit. Mollitia aut
      consectetur quae necessitatibus placeat adipisci facilis
    </p>
    <button class="mt-3 flex gap-1 items-center font-bold">
      Learn more
      <Icon
        icon="radix-icons:chevron-right"
        class="h-[1.2rem] w-[1.2rem]"
      ></Icon>
    </button>

    <div class="basis-2/4 text-center">
      <img
        class="w-[200px] h-[auto] shadow-md mx-auto mt-6 group-hover:scale-110 transition-all duration-500"
        src="/images/invoice2.png"
      />
    </div>
  </div>
</template>
<script setup>
import { Icon } from "@iconify/vue";
</script>
