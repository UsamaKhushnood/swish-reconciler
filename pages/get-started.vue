<script setup lang="ts">
import { toTypedSchema } from "@vee-validate/zod";
import * as z from "zod";
import { h, ref } from "vue";
import Step1 from "@/components/get-started/Step1.vue";
import Step2 from "@/components/get-started/Step2.vue";
import Step3 from "@/components/get-started/Step3.vue";
import Step4 from "@/components/get-started/Step4.vue";
import Step5 from "@/components/get-started/Step5.vue";
import Step6 from "@/components/get-started/Step6.vue";

const formSchema = [
  z.object({
    step1: z.enum(
      [
        "send_invoices",
        "manually",
        "vouchers_for_bank",
        "vouchers_for_sales",
        "none",
      ],
      {
        required_error: "You need to select an option.",
      }
    ),
  }),
  z.object({
    step2: z.enum(
      ["mark_invoices", "sales_and_payout", "only_sales", "only_sales", "help"],
      {
        required_error: "You need to select an option.",
      }
    ),
  }),
  z.object({
    typeOfBusiness: z.union([
      z.literal("coffee"),
      z.literal("tea"),
      z.literal("soda"),
    ]),
    description: z.string(),
  }),
];

const router = useRouter();
const loading = ref(false);
const stepIndex = ref(1);
const steps = [
  {
    step: 1,
    title: "Current Method",
    question: "How do you curretly bookkeep Swish transactions?",
    description:
      "Lorem ipsum dolor sit amet consectetur adipisicing elit. Libero asperiores veniam ratione sed. Soluta est ratione aperiam. Aspernatur libero deleniti dolorem quas! Soluta tempora quam odio ipsum, laborum culpa rem!",
  },
  {
    step: 2,
    title: "Connector Info",
    question: "How would you like a connector to bookkeep?",
    description:
      "Lorem ipsum dolor sit amet consectetur adipisicing elit. Libero asperiores veniam ratione sed. Soluta est ratione aperiam. Aspernatur libero deleniti dolorem quas! Soluta tempora quam odio ipsum, laborum culpa rem!",
  },
  {
    step: 3,
    title: "Business Info",
    question: "What type of business do you run?",
    description:
      "Lorem ipsum dolor sit amet consectetur adipisicing elit. Libero asperiores veniam ratione sed. Soluta est ratione aperiam. Aspernatur libero deleniti dolorem quas! Soluta tempora quam odio ipsum, laborum culpa rem!",
  },
  {
    step: 4,
    title: "Recommendations",
    question: "Recommendations",
    description:
      "Don't worry if you don't have all information right now, you can fill out your company details and configuration settings later.",
  },
  {
    step: 5,
    title: "Info & Configuration",
    question:
      "Fill out your company details and configuration settings to get started.",
    description:
      "Don't worry if you don't have all information right now, you can fill out your company details and configuration settings later.",
  },
  {
    step: 6,
    title: "Connect Bank",
    question: "How would you like a connector to bookkeep?",
    description:
      "Lorem ipsum dolor sit amet consectetur adipisicing elit. Libero asperiores veniam ratione sed. Soluta est ratione aperiam. Aspernatur libero deleniti dolorem quas! Soluta tempora quam odio ipsum, laborum culpa rem!",
  },
  {
    step: 7,
    title: "Business Info",
    question: "What type of business do you run?",
    description:
      "Lorem ipsum dolor sit amet consectetur adipisicing elit. Libero asperiores veniam ratione sed. Soluta est ratione aperiam. Aspernatur libero deleniti dolorem quas! Soluta tempora quam odio ipsum, laborum culpa rem!",
  },
  {
    step: 8,
    title: "Congrats",
    question: "All Done!",
    description:
      "Lorem ipsum dolor sit amet consectetur adipisicing elit. Libero asperiores veniam ratione sed. Soluta est ratione aperiam. Aspernatur libero deleniti dolorem quas! Soluta tempora quam odio ipsum, laborum culpa rem!",
  },
];

function onSubmit(values: any) {
  loading.value = true;
  setTimeout(() => {
    loading.value = false;
    console.log(JSON.stringify(values, null, 2));
    router.push("/recommended-feature");
  }, 2000);
}
</script>

<template>
  <section class="container py-20">
    <h1 class="text-center text-3xl md:text-6xl font-bold md:mt-10 md:mb-20">
      Let's Get Started
    </h1>
    <div>
      <Form
        v-slot="{ meta, values, validate }"
        as=""
        keep-values
        :validation-schema="toTypedSchema(formSchema[stepIndex - 1])"
      >
        <Stepper
          v-slot="{ isNextDisabled, isPrevDisabled, nextStep, prevStep }"
          v-model="stepIndex"
          class="block w-full"
        >
          <form
            @submit="
              (e) => {
                e.preventDefault();
                validate();

                if (stepIndex === steps.length && meta.valid) {
                  onSubmit(values);
                }
              }
            "
          >
            <div class="grid md:grid-cols-2 gap-10">
              <div></div>
              <div class="">
                <div class="flex w-full flex-start gap-2">
                  <StepperItem
                    v-for="step in steps"
                    :key="step.step"
                    v-slot="{ state }"
                    class="relative flex w-full flex-col items-center justify-center"
                    :step="step.step"
                  >
                    <!-- <div class="mt-5 flex flex-col items-center text-center">
                      <StepperTitle
                        :class="[state === 'active' && 'text-primary']"
                        class="text-xs font-semibold transition mb-2"
                      >
                        {{ step.title }}
                      </StepperTitle>
                    </div> -->

                    <StepperTrigger as-child>
                      <Button
                        :variant="
                          state === 'completed' || state === 'active'
                            ? 'default'
                            : 'outline'
                        "
                        size="icon"
                        class="rounded-full border-primary shrink-0 w-[20px] h-[20px]"
                        :class="[
                          state === 'active' &&
                            'ring-1 ring-ring ring-offset-1 ring-offset-background',
                        ]"
                        :disabled="state !== 'completed' && !meta.valid"
                      >
                      </Button>
                    </StepperTrigger>
                    <StepperSeparator
                      v-if="step.step !== steps[steps.length - 1].step"
                      class="absolute left-[calc(50%+20px)] right-[calc(-50%+10px)] bottom-2 block h-0.5 shrink-0 rounded-full bg-muted group-data-[state=completed]:bg-primary"
                    />
                  </StepperItem>
                </div>
              </div>
              <div class="pt-">
                <h1 class="text-4xl font-bold pt-10">
                  {{ steps[stepIndex - 1].question }}
                </h1>
                <p class="mt-3 text-muted-foreground">
                  {{ steps[stepIndex - 1].description }}
                </p>
              </div>
              <div class="bg-gray-50 p-6 md:p-10 rounded-2xl">
                <div class="flex flex-col gap-4">
                  <template v-if="stepIndex === 1">
                    <Step1 />
                  </template>

                  <template v-if="stepIndex === 2">
                    <Step2 />
                  </template>

                  <template v-if="stepIndex === 3">
                    <Step3 />
                  </template>

                  <template v-if="stepIndex === 4">
                    <Step4 />
                  </template>

                  <template v-if="stepIndex === 5">
                    <Step5 />
                  </template>
                  <template v-if="stepIndex === 6">
                    <Step6 />
                  </template>

                  <tempalte v-if="stepIndex === 7">
                    <h1 class="text-xl font-bold mb-3">
                      Finally, lets connect to Fortnox.
                    </h1>
                    <Button
                      size="lg"
                      class="bg-green-900 hover:bg-green-950 py-6 rounded-lg w-full text-xl"
                      >Connect</Button
                    >
                  </tempalte>

                  <template v-if="stepIndex === 8">
                    <h1 class="text-xl font-bold">Congrats, you're all set!</h1>
                    <p>
                      Would you like to activate the services as of tomorrow's
                      date earliest?
                    </p>
                    <RadioGroup default-value="comfortable">
                      <div class="flex items-center space-x-2">
                        <RadioGroupItem id="r1" value="default" />
                        <Label for="r1">Yes, Go!</Label>
                      </div>
                      <div class="flex items-center space-x-2">
                        <RadioGroupItem id="r2" value="comfortable" />
                        <Label for="r2">No, start the sync from date</Label>
                      </div>
                    </RadioGroup>
                  </template>

                  <div class="flex items-center justify-between mt-4">
                    <Button
                      :disabled="isPrevDisabled"
                      variant="outline"
                      @click="prevStep()"
                    >
                      Back
                    </Button>
                    <div
                      class="md:flex text-right space-y-3 md:space-y-0 md:text-start items-center gap-3"
                    >
                      <Button
                        v-if="stepIndex === 4"
                        class="hover:bg-gray-100 hover:text-black"
                        variant="outline"
                        :type="meta.valid ? 'button' : 'submit'"
                        :disabled="isNextDisabled"
                        @click="meta.valid && nextStep()"
                      >
                        No, I need more help
                      </Button>
                      <Button
                        v-if="stepIndex !== steps.length"
                        :type="meta.valid ? 'button' : 'submit'"
                        :disabled="isNextDisabled"
                        @click="meta.valid && nextStep()"
                      >
                        <span v-if="stepIndex === 4"> Sounds right for me</span>
                        <span v-else>Next</span>
                      </Button>
                      <Button
                        :loading="loading"
                        v-if="stepIndex === steps.length"
                        type="submit"
                      >
                        Submit
                      </Button>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </form>
        </Stepper>
      </Form>
    </div>
  </section>
</template>
