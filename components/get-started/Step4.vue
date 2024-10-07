<template>
  <div class="text-xl font-bold">
    <h1>Based on your response, the match we found for your is</h1>
    <h1 class="uppercase text-primary">invoice recoinciler</h1>
    <div>
      <div class="bg-indigo-50 p-6 rounded-3xl basis-2/4 mt-6">
        <h1 class="text-xl font-bold mb-3">How does it work exactly?</h1>
        <ol class="font-normal space-y-1">
          <li>Fetches transaction from bank daily</li>
          <li>Matches with existing invoices</li>
          <li>Marks as paid</li>
        </ol>
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
    </div>
  </div>
</template>
<script setup>
import { MessageCircleQuestion, Info } from "lucide-vue-next";
</script>
