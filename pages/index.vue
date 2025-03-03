<template>
  <main class="min-h-screen">
    <section class="container px-4 mx-auto">
      <div
        class="hero-bg h-[640px] mt-0 md:mt-6 relative rounded-2xl bg-blend-overlay bg-black bg-opacity-75"
        :style="backgroundStyles"
      >
        <div
          class="absolute top-0 left-0 h-full w-full rounded-2xl flex flex-col items-center justify-center"
        >
          <div
            class="flex items-center justify-center flex-col gap-6 text-center p-3 md:p-0"
          >
            <h1
              class="text-[40px] leading-[50px] relative md:text-6xl font-semibold md:font-normal text-white px-2 md:px-0"
            >
              <span class="relative">
                <SVGCrown class="w-16 h-10 md:w-[80px] md:h-[51px] absolute -top-6 -left-7 md:-top-7 md:-left-8" />

                E</span
              >mpowering businesses with <br />
              cutting-edge technology solutions
            </h1>
            <p class="text-base mt-4 font-normal text-white">
              we help businesses rise with solutions
              <br class="block md:hidden" />
              from software development to
              <br class="hidden md:block" />
              AI-driven innovation. Let’s build the future
              <br class="block md:hidden" />
              together.
            </p>
            <div class="mt-8">
              <Button size="lg" variant="light" class="text-black-foreground"
                >Book a session</Button
              >
            </div>
          </div>
        </div>
      </div>
    </section>
  </main>
</template>

<script setup lang="ts">
  import SVGCrown from "@/components/ui/svgs/SVGCrown.vue";
  const img = useImage();
  const backgroundStyles = computed(() => {
    const imgUrl = img("/imgs/together_bg.jpeg");
    return { backgroundImage: `url('${imgUrl}')` };
  });
</script>

<style>
  .hero-bg {
    /* background-image: url('/public/imgs/hero_bg.jpeg'); */
    background-size: cover;
    background-position: center;
    padding: 4rem;
    border-radius: 1rem;
  }
</style>
