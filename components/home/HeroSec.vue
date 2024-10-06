<template>
  <section
    class="bg-[url('/images/herobg.png')] bg-cover bg-center bg-norepeat pt-[100px] md:pt-[200px] pb-[60px] md:min-h-[900px] bg-purple-100 flex flex-col justify-between"
  >
    <div class="container flex">
      <div class="md:basis-3/4 flex flex-col justify-center">
        <h2
          class="text-3xl text-center md:text-start md:text-7xl font-semibold md:font-black text-primary"
        >
          Simplified Bookkeeping for Your Swish Transactions
        </h2>
        <div class="md:flex items-center text-center md:text-start pt-8 gap-4">
          <Button size="lg">Get Started</Button>
          <p class="text-xl font-bold mt-4 md:mt-0">
            Limited-time offer <br />
            50% off for 6 months
          </p>
        </div>
      </div>
    </div>
    <div class="container px-0 md:px-4 md:mt-10 mt-20">
      <h2
        class="font-bold md:text-4xl pb-10 mx-1 md:mx-0 text-center hidden md:block"
      >
        Customers and experts recommend FreshBooks
      </h2>
      <div class="overflow-hidden">
        <Vue3Marquee>
          <div
            v-for="(review, index) in reviews"
            :key="index"
            class="mx-3 md:mx-10"
          >
            <div class="flex items-center">
              <p class="font-bold">{{ review.title }}</p>
              <div class="flex ms-3">
                <Icon
                  icon="radix-icons:star-filled"
                  class="h-[1.2rem] w-[1.2rem] text-yellow-500 cursor-pointer"
                  v-for="i in 5"
                  :key="index"
                />
              </div>
            </div>
            <p>{{ review.comment }}</p>
          </div>
        </Vue3Marquee>
      </div>
    </div>
  </section>
</template>
<script setup>
import { ref } from "vue";
import { Icon } from "@iconify/vue";
const reviews = ref([
  { title: "5 Excellent", comment: "capterra.com" },
  { title: "5 Excellent", comment: "capterra.com" },
  { title: "5 Excellent", comment: "capterra.com" },
  { title: "5 Excellent", comment: "capterra.com" },
  { title: "5 Excellent", comment: "capterra.com" },
  { title: "5 Excellent", comment: "capterra.com" },
  { title: "5 Excellent", comment: "capterra.com" },
  { title: "5 Excellent", comment: "capterra.com" },
  { title: "5 Excellent", comment: "capterra.com" },
]);
</script>
