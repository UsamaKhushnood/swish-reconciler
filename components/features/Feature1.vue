<template>
  <div
    class="bg-amber-50 p-6 md:p-10 hover:shadow-lg shadow-md transition-all group relative col-span-2 h-full flex md:block flex-col justify-center"
  >
    <div class="md:flex">
      <div class="basis-2/4">
        <h1 class="text-xl font-bold">Invoicing</h1>
        <p class="mt-3">
          Lorem, ipsum dolor sit amet consectetur adipisicing elit. Mollitia aut
          consectetur quae necessitatibus placeat adipisci facilis accusantium
          eum facere ducimus quidem ullam, reprehenderit cupiditate et dolor
          nostrum, quasi, ipsum commodi iste voluptatum architecto quod
          consequuntur? Dolore numquam
        </p>
        <button class="mt-3 flex gap-1 items-center font-bold">
          Learn more
          <Icon
            icon="radix-icons:chevron-right"
            class="h-[1.2rem] w-[1.2rem]"
          ></Icon>
        </button>
      </div>
      <div class="basis-2/4 text-center">
        <img
          class="w-[200px] h-[auto] shadow-md absolute hidden lg:block translate-x-1/2 group-hover:translate-y-[-10px] transition-all duration-500"
          src="/images/invoice1.png"
        />
        <img
          class="w-[150px] h-[auto] absolute right-10 hidden lg:block translate-y-2/4 top-0 group-hover:translate-y-3/4 transition-all duration-500 shadow-md"
          src="/images/invoice2.png"
        />
      </div>
    </div>
  </div>
</template>
<script setup>
import { Icon } from "@iconify/vue";
</script>
