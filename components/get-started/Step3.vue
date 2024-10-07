<template>
  <FormField v-slot="{ componentField }" name="typeOfBusiness">
    <FormItem>
      <FormLabel> What type of business do you run? </FormLabel>

      <Select v-bind="componentField">
        <FormControl>
          <SelectTrigger>
            <SelectValue placeholder="Select a drink" />
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
  <FormField v-slot="{ componentField }" name="description">
    <FormItem>
      <FormLabel>Descibe your business a bit more in detail</FormLabel>
      <FormControl>
        <Textarea rows="5" v-bind="componentField" />
      </FormControl>
      <FormMessage />
    </FormItem>
  </FormField>
</template>
