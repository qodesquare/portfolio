<template>
  <Card class="h-[500px] md:w-[480px] md:h-[290px] pt-6 bg-[#F2F2F2] border-none shadow-none">
    <CardHeader class="mb-5 md:mb-0">
      <div class="flex flex-col md:flex-row gap-6 items-center">
        <Avatar class="w-[70px] h-[70px]">
          <AvatarImage :src="avatar" alt="avatar" />
          <AvatarFallback>{{ name[0] }}</AvatarFallback>
        </Avatar>
        <div class="flex flex-col">
          <CardTitle class="text-3xl font-medium">{{ name }}</CardTitle>
          <CardDescription class="text-lg/none text-[#4D4D4D]">
            {{ title }}
          </CardDescription>
        </div>
      </div>
    </CardHeader>
    <CardContent>
      <p class="text-xl/7 md:font-normal text-card-foreground">“<slot></slot>“</p>
    </CardContent>
  </Card>
</template>

<script setup lang="ts">
  defineProps({
    name: String,
    title: String,
    avatar: String,
  });
</script>

<style scoped></style>
