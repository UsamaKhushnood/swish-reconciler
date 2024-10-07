<template>
  <section class="container py-20">
    <h1
      class="text-center text-3xl md:text-6xl font-bold md:mt-10 max-w-4xl mx-auto"
    >
      Based on your response, the match we found for your is
    </h1>
    <h1
      class="text-2xl md:text-5xl font-black text-center uppercase text-primary mt-4 md:mt-10"
    >
      invoice recoinciler
    </h1>
    <div class="md:flex items-cesnter gap-3 mt-10 md:mt-20">
      <div class="bg-indigo-50 p-10 rounded-3xl basis-2/4">
        <h1 class="text-3xl font-bold mb-4">How does it work exactly?</h1>
        <ol class="text-xl space-y-1">
          <li>Fetches transaction from bank daily</li>
          <li>Matches with existing invoices</li>
          <li>Marks as paid</li>
        </ol>
      </div>
      <div
        class="flex flex-col gap-3 items-center justify-center flex-1 bg-pink-50 rounded-3xl p-10 mt-4 md:mt-0"
      >
        <div class="md:flex space-y-3 md:space-y-0 gap-3 w-full pt-6">
          <router-link class="w-full" to="/company-info">
            <Button
              class="bg-indigo-900 hover:bg-indigo-950 w-full py-8 text-2xl rounded-xl"
              >No, I need more help</Button
            >
          </router-link>
          <Button class="w-full py-8 text-2xl rounded-xl">
            Sounds right for me</Button
          >
        </div>
        <div>
          <h4 class="flex items-center gap-2 text-xs">
            <Info />
            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Deleniti,
            quisquam! Ea ducimus sapiente doloribus ipsa enim sequi eum amet
            facere! eum amet facere!
          </h4>
        </div>
      </div>
    </div>
    <div>
      <a
        href="#"
        class="flex items-center gap-1 text-xs px-3 mt-3 hover:underline"
      >
        <MessageCircleQuestion class="text-primary w-[16px]" />
        Give me more detailed info about the service before we proceed to
        purchase
      </a>
    </div>
  </section>
</template>
<script setup>
import { MessageCircleQuestion, Info } from "lucide-vue-next";
</script>
