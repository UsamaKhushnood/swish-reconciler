<template>
  <FormField v-slot="{ componentField }" type="radio" name="step1">
    <FormItem class="space-y-3">
      <FormLabel class="text-2xl">Select an option...</FormLabel>
      <FormControl>
        <RadioGroup class="flex flex-col space-y-1" v-bind="componentField">
          <FormItem class="flex items-center space-x-3 space-y-0">
            <FormControl>
              <RadioGroupItem value="send_invoices" />
            </FormControl>
            <FormLabel class="font-normal">
              I send invoices which are in Fortnox, but they are reconciled.
            </FormLabel>
          </FormItem>
          <FormItem class="flex items-center space-x-3 space-y-0">
            <FormControl>
              <RadioGroupItem value="manually" />
            </FormControl>
            <FormLabel class="font-normal">
              Manually, or not at all.
            </FormLabel>
          </FormItem>
          <FormItem class="flex items-center space-x-3 space-y-0">
            <FormControl>
              <RadioGroupItem value="vouchers_for_bank" />
            </FormControl>
            <FormLabel class="font-normal">
              Manual vouchers for bank payments only
            </FormLabel>
          </FormItem>
          <FormItem class="flex items-center space-x-3 space-y-0">
            <FormControl>
              <RadioGroupItem value="vouchers_for_sales" />
            </FormControl>
            <FormLabel class="font-normal">
              Manual vouchers for sales and bank payments
            </FormLabel>
          </FormItem>
          <FormItem class="flex items-center space-x-3 space-y-0">
            <FormControl>
              <RadioGroupItem value="none" />
            </FormControl>
            <FormLabel class="font-normal"> None of the above </FormLabel>
          </FormItem>
        </RadioGroup>
      </FormControl>
      <FormMessage />
    </FormItem>
  </FormField>
</template>
