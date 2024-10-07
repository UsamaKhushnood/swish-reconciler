<template>
  <div>
    <HeroSec />
    <Features id="features" />
    <WhyUs id="get-started" />
    <Pricing id="pricing" />
    <FAQ id="faqs" />
    <Contact id="contact" />
  </div>
</template>
<script setup>
import HeroSec from "~/components/home/HeroSec.vue";
import Features from "~/components/home/Features.vue";
import WhyUs from "~/components/home/WhyUs.vue";
import Pricing from "~/components/home/Pricing.vue";
import FAQ from "~/components/home/FAQ.vue";
import Contact from "~/components/home/Contact.vue";
</script>
