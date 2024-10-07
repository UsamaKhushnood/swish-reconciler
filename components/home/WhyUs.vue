<template>
  <section class="container pt-10 md:pt-[120px]">
    <div class="bg-indigo-50 py-10 px-6 md:p-20 md:border border-primary">
      <h1
        class="text-center md:text-start text-4xl md:text-6xl font-bold max-w-5xl"
      >
        Need help with
        <span class="text-primary">automating bookkeeping</span> of
        <span class="underline">Swish transactions</span>
      </h1>
      <div
        class="space-y-3 max-w-xl mt-10 border-l-[6px] border-violet-700 pl-6 py-3"
      >
        <p>
          Automatisera Mera provides a integration between banks and Fortnox
          with the purpose of assisting in automatic bookkeping of Swish
          payments.
        </p>
        <p>
          Depending on which type of business you run and what your bookkeeping
          needs are, we have 2 different options which might be suitable for
          you.
        </p>
        <p>
          Let's start with some questions to learn more about your business in
          order to recommend the best solution for you.
        </p>
      </div>
      <router-link to="/get-started">
        <Button size="lg" class="mt-10 px-10 py-4 text-xl mx-auto md:mx-0 flex"
          >Let's Go
        </Button>
      </router-link>
    </div>
  </section>
</template>
