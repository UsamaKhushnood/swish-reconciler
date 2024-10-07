<template>
  <FormField v-slot="{ componentField }" type="radio" name="step2">
    <FormItem class="space-y-3">
      <FormLabel class="text-2xl">Select an option...</FormLabel>
      <FormControl>
        <RadioGroup class="flex flex-col space-y-1" v-bind="componentField">
          <FormItem class="flex items-center space-x-3 space-y-0">
            <FormControl>
              <RadioGroupItem value="mark_invoices" />
            </FormControl>
            <FormLabel class="font-normal">
              Mark our invoices as paid in Fortnox
            </FormLabel>
          </FormItem>
          <FormItem class="flex items-center space-x-3 space-y-0">
            <FormControl>
              <RadioGroupItem value="sales_and_payout" />
            </FormControl>
            <FormLabel class="font-normal">
              Create sales and payout vouchers
            </FormLabel>
          </FormItem>
          <FormItem class="flex items-center space-x-3 space-y-0">
            <FormControl>
              <RadioGroupItem value="only_sales" />
            </FormControl>
            <FormLabel class="font-normal">
              Create only sales vouchers
            </FormLabel>
          </FormItem>
          <FormItem class="flex items-center space-x-3 space-y-0">
            <FormControl>
              <RadioGroupItem value="only_payout" />
            </FormControl>
            <FormLabel class="font-normal">
              Create only payout vouchers
            </FormLabel>
          </FormItem>
          <FormItem class="flex items-center space-x-3 space-y-0">
            <FormControl>
              <RadioGroupItem value="help" />
            </FormControl>
            <FormLabel class="font-normal"> I dont know, help.</FormLabel>
          </FormItem>
        </RadioGroup>
      </FormControl>
      <FormMessage />
    </FormItem>
  </FormField>
</template>
