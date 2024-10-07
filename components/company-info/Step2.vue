<template>
  <FormField v-slot="{ componentField }" name="typeOfBusiness">
    <FormItem>
      <h1 class="text-xl font-bold mb-3">
        Great, now let's get you connected with your bank and Fortnox to
        complete the connection
      </h1>

      <Select v-bind="componentField">
        <FormControl>
          <SelectTrigger>
            <SelectValue placeholder="Select your bank accout" />
          </SelectTrigger>
        </FormControl>
        <SelectContent>
          <SelectGroup>
            <SelectItem value="coffee"> Coffe </SelectItem>
            <SelectItem value="tea"> Tea </SelectItem>
            <SelectItem value="soda"> Soda </SelectItem>
          </SelectGroup>
        </SelectContent>
      </Select>
      <FormMessage />
    </FormItem>
  </FormField>
</template>
