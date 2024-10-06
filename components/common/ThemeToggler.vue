<script setup lang="ts">
import { Icon } from "@iconify/vue";

const colorMode = useColorMode();

const changeTheme = () => {
  if (colorMode.preference === "light") {
    colorMode.preference = "dark";
  } else {
    colorMode.preference = "light";
  }
};
</script>

<template>
  <Button variant="outline" size="icon" class="border-0" @click="changeTheme">
    <Icon
      v-if="colorMode.preference == 'light'"
      icon="radix-icons:moon"
      class="h-[1.2rem] w-[1.2rem]"
    />
    <Icon v-else icon="radix-icons:sun" class="h-[1.2rem] w-[1.2rem]" />
    <span class="sr-only">Toggle theme</span>
  </Button>
</template>
