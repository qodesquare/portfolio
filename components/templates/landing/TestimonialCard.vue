<template>
  <Card
    class="h-[300px] md:w-[480px] md:h-[300px] pt-6 bg-[#F2F2F2] border-none shadow-none text-center flex justify-center items-center"
  >
    <CardContent>
      <CardDescription>
        <p class="text-lg/7 tracking-wider md:font-normal text-card-foreground">
          “<slot></slot>“
        </p>
      </CardDescription>
      <CardHeader class="mb-5 md:mb-0">
        <div class="flex flex-col md:flex-row gap-6 items-center">
          <!-- <Avatar class="w-[70px] h-[70px]">
          <AvatarImage :src="avatar" alt="avatar" />
          <AvatarFallback>{{ name[0] }}</AvatarFallback>
        </Avatar> -->
          <div class="flex flex-col items-center justify-center w-full">
            <CardTitle class="text-2xl font-medium">{{ name }}</CardTitle>
            <CardDescription class="text-base/none text-[#4D4D4D]">
              {{ title }}
            </CardDescription>
          </div>
        </div>
      </CardHeader>
    </CardContent>
  </Card>
</template>

<script setup lang="ts">
  defineProps({
    name: {
      type: String,
      default: "",
    },
    title: String,
    avatar: {
      type: String,
      default: "",
    },
  });
</script>

<style scoped></style>
