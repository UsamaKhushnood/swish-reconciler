<template>
  <section class="py-10 md:py-[120px] container">
    <div class="text-3xl md:text-6xl font-bold text-center">
      <h1>Lorem, ipsum dolor.</h1>
      <h1>
        Marketing <span class="text-primary">Plans</span> and
        <span class="text-primary">Pricing</span>
      </h1>
    </div>
    <Tabs default-value="account" class="w-[340px] mx-auto mt-10 md:mt-20">
      <TabsList class="grid w-full grid-cols-2 rounded-full">
        <TabsTrigger
          class="text-md font-bold py-2 rounded-full"
          value="account"
        >
          Monthly
        </TabsTrigger>
        <TabsTrigger
          class="text-md font-bold py-2 rounded-full"
          value="password"
        >
          Anually
        </TabsTrigger>
      </TabsList></Tabs
    >
    <div
      class="mt-10 md:grid grid-cols-3 gap-4 max-w-6xl mx-auto space-y-6 md:space-y-0"
    >
      <div class="bg-sky-100 rounded-lg p-6 shadow">
        <h1 class="text-4xl font-bold">Basic</h1>
        <p class="text-sm mt-1 text-muted-foreground">
          Up to 50 Montly Conversions
        </p>
        <p class="mt-3 text-sm leading-6">
          Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quis
          temporibus sed alias rerum? Architecto ipsam voluptate beatae
          reprehenderit. Magnam eligendi quae vel accusamus nobis necessitatibus
          quidem similique ipsum perferendis deleniti.
        </p>
        <h1 class="text-4xl font-bold mt-10">$99/mo</h1>
        <Button
          variant="custom"
          class="w-full mt-4 bg-sky-500 rounded-lg py-6 hover:bg-sky-600 text-primary-foreground focus-visible:ring-sky-800"
        >
          Get Started</Button
        >
      </div>
      <div class="bg-orange-50 rounded-lg p-6 shadow">
        <h1 class="text-4xl font-bold">Professional</h1>
        <p class="text-sm mt-1 text-muted-foreground">
          Up to 50 Montly Conversions
        </p>
        <p class="mt-3 text-sm leading-6">
          Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quis
          temporibus sed alias rerum? Architecto ipsam voluptate beatae
          reprehenderit. Magnam eligendi quae vel accusamus nobis necessitatibus
          quidem similique ipsum perferendis deleniti.
        </p>
        <h1 class="text-4xl font-bold mt-10">$99/mo</h1>
        <Button
          variant="custom"
          class="w-full mt-4 bg-orange-500 rounded-lg py-6 hover:bg-orange-600 text-primary-foreground focus-visible:ring-orange-800"
        >
          Get Started</Button
        >
      </div>
      <div class="bg-teal-50 rounded-lg p-6 shadow">
        <h1 class="text-4xl font-bold">Enterprise</h1>
        <p class="text-sm mt-1 text-muted-foreground">
          Up to 50 Montly Conversions
        </p>
        <p class="mt-3 text-sm leading-6">
          Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quis
          temporibus sed alias rerum? Architecto ipsam voluptate beatae
          reprehenderit. Magnam eligendi quae vel accusamus nobis necessitatibus
          quidem similique ipsum perferendis deleniti.
        </p>
        <h1 class="text-4xl font-bold mt-10">Let's talk</h1>
        <Button
          variant="custom"
          class="w-full mt-4 bg-teal-500 rounded-lg py-6 hover:bg-teal-600 text-primary-foreground focus-visible:ring-teal-800"
        >
          Contact Us</Button
        >
      </div>
    </div>
  </section>
</template>
<script setup></script>
