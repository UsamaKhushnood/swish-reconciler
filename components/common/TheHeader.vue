<template>
  <header
    :class="
      cn(
        'sticky top-0 flex h-16 items-center gap-4  z-10 transition-colors duration-300',
        !isScrolled && $route.path == '/' ? 'bg-purple-100' : ' bg-white shadow'
      )
    "
  >
    <div class="container flex items-center">
      <nav
        class="hidden flex-col gap-6 text-lg font-medium md:flex md:flex-row md:items-center md:gap-5 md:text-sm lg:gap-6"
      >
        <router-link
          to="/"
          class="flex items-center gap-2 text-lg font-bold md:text-base whitespace-nowrap"
        >
          Swish Reconciler
        </router-link>
        <a
          v-for="(link, index) in navLinks"
          :key="index"
          :href="link.href"
          class="text-muted-foreground transition-colors hover:text-foreground"
        >
          {{ link.text }}
        </a>
      </nav>
      <Sheet>
        <SheetTrigger as-child>
          <Button variant="outline" size="icon" class="shrink-0 md:hidden">
            <Icon
              icon="radix-icons:hamburger-menu"
              class="h-[1.2rem] w-[1.2rem]"
            />
            <span class="sr-only">Toggle navigation menu</span>
          </Button>
        </SheetTrigger>
        <SheetContent class="rounded-e-xl" side="left">
          <nav class="grid gap-3 text-lg font-medium">
            <router-link
              to="/"
              class="text-lg font-bold md:text-base whitespace-nowrap mb-10"
            >
              Swish Reconciler
            </router-link>
            <a
              v-for="(link, index) in navLinks"
              :key="index"
              :href="link.href"
              class="text-muted-foreground transition-colors hover:text-foreground"
            >
              {{ link.text }}
            </a>
          </nav>
        </SheetContent>
      </Sheet>
      <div class="ms-auto flex gap-2">
        <Button variant="outline" class="hover:bg-gray-100 hover:text-black"
          >Login</Button
        >
        <Button>Sign Up</Button>
      </div>
    </div>
  </header>
</template>
<script setup>
import { ref, onMounted, onUnmounted } from "vue";
import { cn } from "@/lib/utils";
import { Icon } from "@iconify/vue";

const isScrolled = ref(false);

const handleScroll = () => {
  isScrolled.value = window.scrollY > 50;
};

onMounted(() => {
  window.addEventListener("scroll", handleScroll);
});

onUnmounted(() => {
  window.removeEventListener("scroll", handleScroll);
});

const navLinks = ref([
  { text: "Home", href: "/#" },
  { text: "Features", href: "/#features" },
  { text: "Get Started", href: "/#get-started" },
  { text: "Plans & Pricing", href: "/#pricing" },
  { text: "FAQ's", href: "/#faqs" },
  { text: "Contact", href: "/#contact" },
]);
</script>
