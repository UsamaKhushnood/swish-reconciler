<template>
  <div class="bg-black py-1">
    <Vue3Marquee :duration="30" clone>
      <h6
        class="mx-1 font-bold text-primary-foreground flex items-center gap-1"
        v-for="(text, x) in marquee"
        :key="x"
      >
        {{ text }}
        <Icon icon="radix-icons:dot-filled" class="h-[1.2rem] w-[1.2rem]" />
      </h6>
    </Vue3Marquee>
  </div>
  <div class="container py-20">
    <div class="md:flex justify-between">
      <div class="flex flex-col">
        <div>
          <a href="#" class="flex gap-2 font-bold text-2xl">
            Swish Reconciler</a
          >
          <p class="text-sm">
            Simplified Bookkeeping for Your Swish Transactions
          </p>
        </div>
        <div class="flex gap-2 text-xs font-light mt-6">
          <Icon
            icon="hugeicons:facebook-01"
            class="h-[1.2rem] w-[1.2rem] hover:text-primary cursor-pointer"
          />
          <Icon
            icon="hugeicons:instagram"
            class="h-[1.2rem] w-[1.2rem] hover:text-primary cursor-pointer"
          />
          <Icon
            icon="hugeicons:linkedin-01"
            class="h-[1.2rem] w-[1.2rem] hover:text-primary cursor-pointer"
          />
          <Icon
            icon="hugeicons:whatsapp"
            class="h-[1.2rem] w-[1.2rem] hover:text-primary cursor-pointer"
          />
        </div>
      </div>
      <div>
        <div
          class="grid md:grid-cols-3 grid-cols-2 md:gap-20 gap-6 my-10 md:my-0"
        >
          <div
            class="md:py-0 py-4"
            v-for="(data, index) in footerLinks"
            :key="index"
          >
            <h6 class="text-sm text-muted-foreground font-semibold pb-4">
              {{ data.heading }}
            </h6>
            <div class="grid gap-4">
              <p
                class="font-semibold text-sm hover:text-primary cursor-pointer"
                v-for="(link, i) in data.links"
                :key="i"
              >
                {{ link }}
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="mt-10">
      <h1 class="font-bold text-lg">Simplify Your Swish Transactions</h1>
      <div
        class="md:flex flex-grow-1 flex-1 items-center justify-between text-sm text-muted-foreground"
      >
        <p>Managing Swish transactions has never been easier.</p>
        <p class="mt-10 md:mt-0 text-center md:text-start">
          &copy; {{ new Date().getFullYear() }} Swish Reconciler, Inc. All
          rights reserved.
        </p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
import { Icon } from "@iconify/vue";

const footerLinks = ref([
  {
    heading: "Solution",
    links: ["Marketing", "Analytics", "Common", "Insight"],
  },
  {
    heading: "Support",
    links: ["Pricing", "Documentation", "Guides", "API Status"],
  },
  {
    heading: "Company",
    links: ["About", "Blog", "Job", "Press", "Partners"],
  },
]);

const marquee = ref([
  "How it works",
  "Documentation",
  "Guides",
  "API Status",
  "Pricing",
  "Subscribe to newsletter",
]);
</script>
