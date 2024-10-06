<template>
  <section class="bg-purple-100">
    <div class="bg-white md:rounded-tl-[200px]">
      <div class="container pt-20 md:pt-[120px] pb-10 md:pb-0">
        <div class="text-center text-3xl md:text-6xl font-bold">
          <h1>The <span class="text-primary">features</span> you need.</h1>
          <div>All in one place.</div>
        </div>
        <Carousel
          :opts="{
            align: 'start',
            loop: true,
          }"
          class="block md:hidden relative w-full mt-10"
          @init-api="setApi"
        >
          <CarouselContent>
            <CarouselItem class="basis-[90%] pl-3">
              <Feature1 />
            </CarouselItem>
            <CarouselItem class="basis-[90%] pl-3">
              <Feature2 />
            </CarouselItem>
            <CarouselItem class="basis-[90%] pl-3">
              <Feature3 />
            </CarouselItem>
            <CarouselItem class="basis-[90%] pl-3">
              <Feature4 />
            </CarouselItem>
            <CarouselItem class="basis-[90%] pl-3">
              <Feature5 />
            </CarouselItem>
          </CarouselContent>
        </Carousel>

        <div class="flex justify-center gap-2 mt-4 md:hidden">
          <button
            v-for="index in totalCount"
            :key="index"
            @click="api?.scrollTo(index - 1)"
            class="w-3 h-3 rounded-full transition-all duration-300"
            :class="current === index ? 'bg-primary' : 'bg-gray-300'"
          ></button>
        </div>

        <div class="my-10 hidden md:grid grid-cols-3 gap-4 max-w-7xl mx-auto">
          <Feature1 />
          <Feature2 />
          <Feature3 />
          <Feature4 />
          <Feature5 />
        </div>
      </div>
    </div>
  </section>
</template>
<script setup lang="ts">
import { ref, onMounted } from "vue";
import { watchOnce } from "@vueuse/core";
import { Icon } from "@iconify/vue";
import type { CarouselApi } from "@/components/ui/carousel";
import Feature1 from "@/components/features/Feature1.vue";
import Feature2 from "@/components/features/Feature2.vue";
import Feature3 from "@/components/features/Feature3.vue";
import Feature4 from "@/components/features/Feature4.vue";
import Feature5 from "@/components/features/Feature5.vue";

const api = ref<CarouselApi>();
const totalCount = ref(0);
const current = ref(0);

function setApi(val: CarouselApi) {
  api.value = val;
}

watchOnce(api, (api) => {
  if (!api) return;

  totalCount.value = api.scrollSnapList().length;
  current.value = api.selectedScrollSnap() + 1;

  api.on("select", () => {
    current.value = api.selectedScrollSnap() + 1;
  });
});

onMounted(() => {
  current.value = 1;
});
</script>
