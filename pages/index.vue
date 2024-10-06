<template>
  <div>
    <HeroSec />
    <Features id="features" />
    <Pricing />
    <FAQ />
    <Contact />
  </div>
</template>
<script setup>
import HeroSec from "~/components/home/HeroSec.vue";
import Features from "~/components/home/Features.vue";
import Pricing from "~/components/home/Pricing.vue";
import FAQ from "~/components/home/FAQ.vue";
import Contact from "~/components/home/Contact.vue";
</script>
