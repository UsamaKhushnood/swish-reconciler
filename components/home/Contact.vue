<template>
  <div class="md:pt-20">
    <div class="bg-violet-100 mb-10 rounded-3xl mx-0 md:mx-10">
      <div class="container p-0 md:px-4 py-10 pb-2 md:pb-20 md:py-20">
        <div class="md:flex justify-between items-center gap-10">
          <div class="px-6 md:px-0">
            <h1 class="text-3xl md:text-6xl font-bold md:font-semibold">
              Contact Us
            </h1>
            <p class="text-sm mt-2">
              Email, call or fill out our form to learn how <br />Swish
              Reconciler can solve your bookkeeping problems.
            </p>
            <div class="flex flex-col text-sm gap-1 text-muted-foreground mt-3">
              <a class="w-fit" href="mailto:info@swishrecounciler.com"
                >info@swishrecounciler.com</a
              >
              <a class="w-fit" href="phone:23233333">321-3221 332</a>
              <a href="#" class="underline w-fits text-black"
                >Customer Support</a
              >
            </div>
            <div class="hidden md:grid grid-cols-2 gap-6 mt-10">
              <div v-for="x in 3" :key="x">
                <h1 class="font-bold text-lg">Customer Support</h1>
                <p class="text-xs mt-1 text-muted-foreground max-w-xs">
                  Lorem ipsum dolor sit amet consectetur adipisicing elit.
                  Inventore consequuntur provident voluptatem consequuntur
                  provident voluptatem.
                </p>
              </div>
            </div>
          </div>
          <div
            class="bg-white max-w-md shadow-lg rounded-xl p-6 mt-10 md:mt-0 mx-2 md:mx-0"
          >
            <h1 class="text-3xl font-bold">Get in touch</h1>
            <p class="text-muted-foreground text-sm">
              You can reach us anytime
            </p>
            <div class="space-y-3">
              <div
                class="md:grid space-y-3 md:space-y-0 grid-cols-2 gap-3 mt-6"
              >
                <Input placeholder="First name" />
                <Input placeholder="Last name" />
              </div>
              <Input placeholder="Email" />
              <Input placeholder="Phone" />
              <Textarea rows="6" placeholder="How we can help?" />
              <Button class="w-full">Submit</Button>
              <p
                class="text-center text-xs text-muted-foreground max-w-xs mx-auto"
              >
                By contacting us, you agree to our
                <a href="#" class="text-black">Terms of service</a> and
                <a href="#" class="text-black">Privacy Policy</a>
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
