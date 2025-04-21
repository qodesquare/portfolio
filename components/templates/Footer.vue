<template>
  <footer class="h-[500px]">
    <div
      class="bg-center contain h-full bg-no-repeat bg-[auto_380px] md:bg-[auto_480px] lg:bg-[auto_490px] text-center flex flex-col items-center justify-center gap-4"
      :style="footerBackgroundStyle"
    >
      <div
        class="flex flex-col gap-4 items-center md:justify-center justify-center grow-[7]"
      >
        <h2
          class="font-semibold text-4xl/[50px] md:text-5xl/[50px] max-w-xs md:max-w-lg lg:max-w-4xl"
        >
          Let’s Build Something Great for your business together
        </h2>
        <div class="flex items-center justify-center space-x-2 w-full">
          <div class="flex justify-center -space-x-5">
            <Avatar
              class="border-2 border-white"
              v-for="avatar in avatars"
              :key="avatar"
            >
              <AvatarImage
                :src="avatar"
                alt="avatar"
                class="w-6 h-6 bg-[#CAC2FF]"
              />
              <AvatarFallback>{{ avatar }}</AvatarFallback>
            </Avatar>
          </div>
          <p class="text-base/none">+ 10 Businesses trust our solutions</p>
        </div>
        <div class="mt-4">
          <NuxtLink to="https://tr.ee/aklRqL" target="_blank"
            ><Button>Book a session</Button></NuxtLink
          >
        </div>
      </div>
      <div
        class="flex flex-col lg:flex-row items-center justify-between w-full lg:px-20 lg:pb-10 grow-1 container mx-auto"
      >
        <ul class="items-center gap-8 flex mt-14 lg:mt-0">
          <li
            v-for="link in appInfo.navLinks"
            :key="link.url"
            class="w-full group transition-all duration-500"
          >
            <NuxtLink
              :to="link.url"
              class="group-hover:underline underline-offset-4 decoration-2"
              >{{ link.name }}
            </NuxtLink>
          </li>
        </ul>
        <div class="my-4 lg:my-0">
          <p class="text-base/none">
            &copy;{{ new Date().getFullYear() }} Qodesquare. All rights reserved
          </p>
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup lang="ts">
  const img = useImage();
  const footerBackgroundStyle = computed(() => {
    const imgUrl = img("/logo_bg.svg");
    return { backgroundImage: `url('${imgUrl}')` };
  });

  const avatars = ["/imgs/av3.png", "/imgs/av2.png", "/imgs/av1.png"];

  // TODO: Send this information from server
  const appInfo = ref({
    logo: "/imgs/logo.svg",
    navLinks: [
      { name: "Home", url: "/" },
      { name: "Services", url: "#services" },
      { name: "Careers", url: "/careers" },
    ],
  });
</script>

<style scoped></style>
