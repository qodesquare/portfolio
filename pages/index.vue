<template>
  <main class="min-h-screen">
    <section class="container px-4 mx-auto mb-36">
      <div
        class="hero-bg h-[723px] md:h-[620px] mt-0 md:mt-6 relative rounded-2xl bg-blend-overlay bg-black bg-opacity-75"
        :style="heroBackgroundStyle"
      >
        <div
          class="absolute top-0 left-0 h-full w-full rounded-2xl flex flex-col items-center justify-center"
        >
          <div
            class="flex items-center justify-center flex-col gap-6 md:gap-9 text-center mt-[100px] px-3 md:p-0"
          >
            <img src="/white-logo.svg" alt="logo" class="w-[28px]" />
            <h1
              class="text-[40px] leading-[50px] relative md:text-6xl font-semibold md:font-normal text-white px-2 md:px-0"
            >
              <span class="relative">
                <SVGCrown
                  class="w-16 h-10 md:w-[80px] md:h-[51px] absolute -top-6 -left-7 md:-top-7 md:-left-8"
                />

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
              <!-- <Button variant="light" class="text-black-foreground block md:hidden"
                >Book a session</Button
              > -->
            </div>
            <div class="grid grid-cols-12 md:grid-cols-9 gap-4 md:gap-0">
              <SVGPointer class="col-start-3 w-20 md:w-28 md:col-start-4" />
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Our Approach -->
    <section class="bg-black px-0 mb-36 overflow-hidden relative md:p-24 p-0">
      <div
        class="bg-cover text-white text-4xl/[3rem] md:text-5xl/[3.5rem] font-medium flex items-center justify-center text-center bg-center md:bg-contain bg-no-repeat h-[720px] md:h-[550px] px-7"
        :style="earthBackgroundStyle"
      >
        Our Approach is human centric <br />
        We develop functional <br class="block md:hidden" />
        solutions that improve <br class="hidden md:block" />
        products <br class="block md:hidden" />
        and services on <br class="block md:hidden" />
        Global standards
      </div>

      <!-- <div class="grid grid-cols-12 gap-4 absolute">
        <div class="col-span-12 md:col-span-6">
          <h2 class="text-2xl font-semibold text-black-foreground">
            Our Services
          </h2>
          <p class="text-base mt-4 font-normal text-black-foreground">
            We provide a wide range of services to help businesses grow and
            succeed. From software development to AI-driven innovation, we have
            the expertise to help you build the future.
          </p>
        </div>
      </div> -->
    </section>

    <!-- Our Services -->
    <section class="container px-4 mx-auto mb-36">
      <div class="flex flex-col gap-20">
        <h2
          class="text-4xl md:text-5xl font-semibold text-black-foreground text-center flex items-center justify-center"
        >
          Why do you <br />
          need our services?
        </h2>

        <div class="grid grid-cols-4 gap-6">
          <Card
            class="col-span-4 md:col-span-2 bg-[#F2F2F2] border-none shadow-none h-[240px] md:h-auto"
          >
            <CardContent class="grid grid-cols-3 p-6 align-bottom h-full">
              <p
                class="md:text-4xl text-xl font-semibold col-span-2 justify-self-end self-end"
              >
                Challenges That Might Be Holding Your Business Back
              </p>
              <img
                src="/imgs/arrow.svg"
                alt="arrow"
                class="w-[38px] md:w-[60px] justify-self-end self-end transform rotate-90 md:rotate-0 -translate-y-4"
              />
            </CardContent>
          </Card>
          <div
            class="grid grid-cols-1 md:grid-cols-2 md:col-span-2 col-span-4 gap-6"
          >
            <Card
              class="h-[230px] border-none shadow-none bg-cover bg-center"
              :style="{ backgroundImage: `url(${service.bgImg})` }"
              v-for="service in services"
              :key="service.desc"
            >
              <CardContent
                class="bg-black/60 text-white font-semibold flex items-end h-full rounded-xl p-4"
              >
                <p
                  class="inlinne-block align-text-bottom font-medium leading-6"
                >
                  {{ service.desc }}
                </p>
              </CardContent>
            </Card>
          </div>
        </div>
      </div>
    </section>
  </main>
</template>

<script setup lang="ts">
  import SVGCrown from "@/components/ui/svgs/SVGCrown.vue";
  import SVGPointer from "@/components/ui/svgs/SVGPointer.vue";
  import SVGEarth from "@/components/ui/svgs/SVGEarth.vue";

  const img = useImage();
  const heroBackgroundStyle = computed(() => {
    const imgUrl = img("/imgs/together_bg.jpeg");
    return { backgroundImage: `url('${imgUrl}')` };
  });

  const earthBackgroundStyle = computed(() => {
    const imgUrl = img("/imgs/earth.svg");
    return { backgroundImage: `url('${imgUrl}')` };
  });

  const services = [
    {
      desc: "An outdated or confusing website makes it hard for people to trust or reach your business.",
      bgImg: "/imgs/service1.jpeg",
    },
    {
      desc: "Your business runs on too much manual work, repetitive tasks and time waste that makes work harder.",
      bgImg: "/imgs/service2.jpeg",
    },
    {
      desc: "You struggle to attract customers, no online presence which makes it tough to get to more audience.",
      bgImg: "/imgs/service3.jpeg",
    },
    {
      desc: "Slow business growth which makes it difficult to stay ahead of the competition.",
      bgImg: "/imgs/service4.jpeg",
    },
  ];
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
