<template>
  <section class="py-10 md:py-[120px] container">
    <h1 class="text-3xl md:text-6xl font-bold text-center">
      Frequently Asked <span class="text-primary">Questions</span>
    </h1>
    <div class="mt-10 mx-auto max-w-4xl">
      <Accordion
        type="single"
        class="w-full"
        collapsible
        :default-value="defaultValue"
      >
        <AccordionItem
          class="data-[state=open]:my-4 my-1 rounded-md data-[state=open]:rounded-xl data-[state=open]:bg-purple-50 data-[state=open]:border-primary transition-all duration-200 border data-[state=open]:border hover:bg-purple-50 hover:border-primary"
          v-for="item in accordionItems"
          :key="item.value"
          :value="item.value"
        >
          <AccordionTrigger
            class="hover:no-underline px-6 font-bold text-md text-start"
            >{{ item.title }}</AccordionTrigger
          >
          <AccordionContent class="px-6">
            {{ item.content }}
          </AccordionContent>
        </AccordionItem>
      </Accordion>
    </div>
  </section>
</template>
<script setup>
import {
  Accordion,
  AccordionContent,
  AccordionItem,
  AccordionTrigger,
} from "@/components/ui/accordion";

const defaultValue = "item-1";
const accordionItems = [
  {
    value: "item-1",
    title: "Is it accessible?",
    content:
      "Yes. It adheres to the WAI-ARIA design pattern.Yes. It adheres to the WAI-ARIA design pattern.Yes. It adheres to the WAI-ARIA design pattern.Yes. It adheres to the WAI-ARIA design pattern.Yes. It adheres to the WAI-ARIA design pattern.Yes. It adheres to the WAI-ARIA design pattern.Yes. It adheres to the WAI-ARIA design pattern.Yes. It adheres to the WAI-ARIA design pattern.",
  },
  {
    value: "item-2",
    title: "Is it unstyled?",
    content:
      "Yes. It's unstyled by default, giving you freedom over the look and feel.Yes. It's unstyled by default, giving you freedom over the look and feel.Yes. It's unstyled by default, giving you freedom over the look and feel. Yes. It's unstyled by default, giving you freedom over the look and feel.",
  },
  {
    value: "item-3",
    title: "Can it be animated?",
    content: "Yes! You can use the transition prop to configure the animation.",
  },
  {
    value: "item-4",
    title: "Is it customizable?",
    content:
      "Yes, you can customize the behavior and appearance to fit your specific needs with custom props.",
  },
  {
    value: "item-5",
    title: "Does it support keyboard navigation?",
    content:
      "Absolutely! The component is designed with full keyboard navigation support.",
  },
  {
    value: "item-6",
    title: "Can I add custom icons?",
    content:
      "Yes, you can add your own icons to the headers or any other parts of the accordion.",
  },
  {
    value: "item-7",
    title: "Is it responsive?",
    content:
      "Yes, the accordion is fully responsive and works seamlessly on mobile, tablet, and desktop devices.",
  },
  {
    value: "item-8",
    title: "Does it support nested accordions?",
    content:
      "Yes, you can create nested accordions for more complex layouts and interactions.",
  },
  {
    value: "item-9",
    title: "Is it compatible with Vue 3?",
    content:
      "Yes, this component is fully compatible with Vue 3 and takes advantage of the new features in Vue 3.",
  },
  {
    value: "item-10",
    title: "How do I style it?",
    content:
      "You can style the accordion by applying custom CSS classes or integrating it with a CSS framework like Tailwind CSS.",
  },
  {
    value: "item-11",
    title: "Can I control which items are open by default?",
    content:
      "Yes, you can set which accordion items are open by default using the `defaultOpen` prop.",
  },
  {
    value: "item-12",
    title: "Does it work with dynamic content?",
    content:
      "Yes, the accordion can handle dynamic content and will update as new items are added or removed.",
  },
];
</script>
