<template>
  <div class="space-y-3">
    <h1 class="text-xl font-bold">Company details</h1>
    <div class="grid gap-3 grid-cols-2" v-for="x in 3" :key="x">
      <FormField v-slot="{ componentField }" name="fullName">
        <FormItem>
          <FormControl>
            <Input
              placeholder="Company name"
              type="text"
              v-bind="componentField"
            />
          </FormControl>
          <FormMessage />
        </FormItem>
      </FormField>
      <FormField v-slot="{ componentField }" name="fullName">
        <FormItem>
          <FormControl>
            <Input
              placeholder="Bank name"
              type="text"
              v-bind="componentField"
            />
          </FormControl>
          <FormMessage />
        </FormItem>
      </FormField>
    </div>
    <h1 class="text-xl font-bold">Configuration details</h1>
    <div class="grid gap-3 grid-cols-2">
      <FormField v-slot="{ componentField }" name="fullName">
        <FormItem>
          <FormControl>
            <Input
              placeholder="Payout account"
              type="text"
              v-bind="componentField"
            />
          </FormControl>
          <FormMessage />
        </FormItem>
      </FormField>
      <FormField v-slot="{ componentField }" name="fullName">
        <FormItem>
          <FormControl>
            <Input
              placeholder="Voucher series"
              type="text"
              v-bind="componentField"
            />
          </FormControl>
          <FormMessage />
        </FormItem>
      </FormField>
    </div>
    <div class="grid grid-cols-2 gap-3 w-full">
      <FormField name="items" v-for="x in 2" :key="x">
        <FormItem>
          <h1 class="text-sm mb-3 font-bold">
            How would you like voucher posted?
          </h1>
          <FormField
            v-for="item in items"
            v-slot="{ value, handleChange }"
            :key="item.id"
            name="items"
          >
            <FormItem
              :key="item.id"
              class="flex flex-row items-start space-x-3 space-y-0"
            >
              <FormControl>
                <Checkbox :checked="value.includes(item.id)" />
              </FormControl>
              <FormLabel class="font-normal">
                {{ item.label }}
              </FormLabel>
            </FormItem>
          </FormField>
          <FormMessage />
        </FormItem>
      </FormField>
    </div>
  </div>
</template>
<script setup lang="ts">
import { useForm } from "vee-validate";
import { toTypedSchema } from "@vee-validate/zod";
import * as z from "zod";

const items = [
  {
    id: "Both",
    label: "Both",
  },
  {
    id: "only_sales",
    label: "Only Sales Voucher",
  },
  {
    id: "only_payout",
    label: "Only Payout",
  },
] as const;

const displayFormSchema = toTypedSchema(
  z.object({
    items: z.array(z.string()).refine((value) => value.some((item) => item), {
      message: "You have to select at least one item.",
    }),
  })
);

const { handleSubmit } = useForm({
  validationSchema: displayFormSchema,
  initialValues: {
    items: ["recents", "home"],
  },
});

const onSubmit = handleSubmit((values) => {
  console.log(values);
});
</script>
