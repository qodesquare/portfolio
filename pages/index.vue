<template>
  <main class="min-h-screen">
    <Section>
      <div
        class="hero-bg h-[723px] md:h-[620px] mt-0 md:mt-6 relative rounded-2xl bg-blend-overlay bg-black bg-opacity-75"
        :style="heroBackgroundStyle"
      >
        <div
          class="absolute top-0 left-0 h-full w-full rounded-2xl flex flex-col items-center justify-center"
        >
          <div
            class="flex items-center justify-center flex-col gap-6 md:gap-8 lg:gap-9 text-center mt-[100px] px-3 md:p-0"
          >
            <img src="/white-logo.svg" alt="logo" class="w-[28px]" />
            <h1
              class="text-4xl md:px-16 leading-[50px] relative lg:text-6xl font-semibold md:font-normal text-white px-2 lg:px-0"
            >
              <span class="relative">
                <SVGCrown
                  class="w-16 h-10 md:w-[80px] md:h-[51px] absolute -top-6 -left-7 md:-top-7 md:-left-8"
                />

                E</span
              >mpowering businesses with <br />
              cutting-edge technology <br class="md:hidden block" />
              solutions
            </h1>
            <p class="text-base mt-5 font-normal text-white">
              we help businesses rise with solutions
              <br class="block md:hidden" />
              from software development to
              <br class="hidden md:block" />
              AI-driven innovation. Let’s build the future
              <br class="block md:hidden" />
              together.
            </p>
            <div class="mt-8">
              <NuxtLink to="https://tr.ee/kknw56" target="_blank">
                <Button size="lg" variant="light" class="text-black-foreground"
                  >Book a session</Button
                >
              </NuxtLink>
            </div>
            <div class="grid grid-cols-12 md:grid-cols-9 gap-4 md:gap-0">
              <SVGPointer class="col-start-3 w-20 md:w-28 md:col-start-4" />
            </div>
          </div>
        </div>
      </div>
    </Section>

    <!-- Our Approach -->
    <Section
      class="bg-black px-0 mb-36 overflow-hidden relative md:p-24 p-0"
      :container="false"
    >
      <!-- <section class="bg-black px-0 mb-36 overflow-hidden relative md:p-24 p-0"> -->
      <div
        class="bg-cover text-white text-4xl/[3rem] lg:text-5xl/[3.5rem] font-medium flex items-center justify-center text-center bg-center md:bg-contain bg-no-repeat h-[720px] md:h-[450px] lg:h-[550px] px-7"
        :style="earthBackgroundStyle"
      >
        Our Approach is human centric <br />
        We develop functional <br class="block md:hidden" />
        solutions that improve <br class="hidden md:block" />
        products <br class="block md:hidden" />
        and services on <br class="block md:hidden" />
        Global standards
      </div>
    </Section>

    <!-- Our Services -->
    <Section>
      <div class="flex flex-col gap-20">
        <h2
          class="text-3xl md:text-4xl font-semibold text-black-foreground text-center flex items-center justify-center"
        >
          Why do you <br />
          need our services?
        </h2>

        <div class="grid grid-cols-4 gap-6">
          <Card
            class="col-span-4 lg:col-span-2 bg-[#F2F2F2] border-none shadow-none h-[240px] md:h-[280px] lg:h-auto"
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
                class="w-[38px] md:w-[60px] justify-self-end self-end transform rotate-90 lg:rotate-0 -translate-y-4"
              />
            </CardContent>
          </Card>
          <div
            class="grid grid-cols-1 lg:grid-cols-2 lg:col-span-2 col-span-4 gap-6"
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
                  class="text-xl inlinne-block align-text-bottom font-medium leading-6"
                >
                  {{ service.desc }}
                </p>
              </CardContent>
            </Card>
          </div>
        </div>
      </div>
    </Section>
    <!-- Our Solutions -->
    <Section id="services">
      <div class="flex flex-col gap-20">
        <h2
          class="text-3xl md:text-4xl font-semibold text-black-foreground text-center flex items-center justify-center"
        >
          Solutions We Offer,<br />
          Tailored for You
        </h2>

        <div class="grid grid-cols-1 lg:grid-cols-3 gap-6">
          <Card
            class="h-[549px] border-none shadow-none bg-cover bg-center"
            :style="{ backgroundImage: `url(${solution.bgImg})` }"
            v-for="solution in solutions"
            :key="solution.desc"
          >
            <CardContent
              class="bg-black/60 text-white font-semibold flex flex-col justify-end h-full rounded-xl p-4 gap-8"
            >
              <CardHeader class="text-white font-semibold text-2xl p-0">
                {{ solution.title }}
              </CardHeader>
              <p
                class="inlinne-block align-text-bottom font-light leading-8 text-xl md:text-2xl"
              >
                {{ solution.desc }}
              </p>
              <p class="flex gap-2 p-0 text-2xl font-normal">
                Let's Talk
                <img src="/imgs/arrow-up-right.svg" alt="arrow" class="w-6" />
              </p>
            </CardContent>
          </Card>
        </div>
      </div>
    </Section>
    <!-- Our Work -->
    <Section>
      <div class="flex flex-col gap-20">
        <h2
          class="text-3xl md:text-4xl font-semibold text-black-foreground text-center flex items-center justify-center"
        >
          Our Work, Tailored <br />
          for your Success
        </h2>

        <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
          <Card
            class="h-[549px] border-none shadow-none bg-cover bg-center"
            :style="{ backgroundImage: `url(${work.bgImg})` }"
            v-for="work in works"
            :key="work.text"
            is="a"
            :href="work.link"
            target="_blank"
          >
            <CardContent
              class="bg-black/50 text-white font-semibold flex flex-col justify-end h-full rounded-xl p-4 gap-8"
            >
              <CardHeader class="text-white font-semibold text-2xl/9 p-0">
                {{ work.text }}
              </CardHeader>
              <p class="flex gap-2 p-0 text-2xl font-semibold" target="_blank">
                Visit Site
                <img src="/imgs/arrow-up-right.svg" alt="arrow" class="w-6" />
              </p>
            </CardContent>
          </Card>
        </div>
      </div>
    </Section>
    <!-- Testimonies -->
    <Section class="mb-2">
      <div class="flex flex-col gap-20">
        <h2
          class="text-3xl md:text-4xl font-semibold text-black-foreground text-center flex items-center justify-center"
        >
          Trusted by Businesses and <br />
          individuals Like Yours
        </h2>

        <div class="grid grid-cols-1 gap-6">
          <Testimonials :testimonials="testimonials" />
        </div>
      </div>
    </Section>
    <Footer />
  </main>
</template>

<script setup lang="ts">
  import SVGCrown from "@/components/ui/svgs/SVGCrown.vue";
  import SVGPointer from "@/components/ui/svgs/SVGPointer.vue";
  import Testimonials from "@/components/templates/landing/Testimonials.vue";
  import Section from "@/components/templates/Section.vue";
  import Footer from "@/components/templates/Footer.vue";

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
  const solutions = [
    {
      desc: "A confusing or unattractive website drives customers away. We create easy-to-use, visually appealing designs that make your business stand out and keep users engaged",
      bgImg: "/imgs/sol3.jpeg",
      title: "Product Design",
    },
    {
      desc: "Slow, outdated systems can cost you time and money. We build fast, reliable websites and software that help you work smarter and serve customers better.",
      bgImg: "/imgs/sol2.jpeg",
      title: "Software & Web Development",
    },
    {
      desc: "Repetitive tasks waste valuable time. We use AI to automate processes, improve customer interactions, and help your business run more efficiently.",
      bgImg: "/imgs/sol1.jpeg",
      title: "AI Automation",
    },
  ];

  const works = [
    {
      bgImg: "/imgs/asup-work.png",
      text: "ACADEMIC STAFF UNION OF POLYTECHNICS(ASUP) Nigeria.",
      link: "https://asupng.org/",
    },
    {
      bgImg: "/imgs/agile-work.png",
      text: "ADOLESCENT GIRLS INITIATIVE FOR LEARNING AND EMPOWERMENT(AGILE) PROJECT.",
      link: "https://agileproject.education.gov.ng/",
    },
  ];

  const testimonials = [
    {
      name: "Edet Effiong",
      title: "Head of operations, Battery alliance services ",
      avatar: "/imgs/sol1.jpeg",
      text: "Working with qodespace transformed our business. Their tech solutions streamlined our processes and boosted efficiency by 40%!",
    },
    {
      name: "Edet Effiong",
      title: "Head of operations, Battery alliance services ",
      avatar: "/imgs/sol1.jpeg",
      text: "Working with qodespace transformed our business. Their tech solutions streamlined our processes and boosted efficiency by 40%!",
    },
    {
      name: "Edet Effiong",
      title: "Head of operations, Battery alliance services ",
      avatar: "/imgs/sol1.jpeg",
      text: "Working with qodespace transformed our business. Their tech solutions streamlined our processes and boosted efficiency by 40%!",
    },
    {
      name: "Edet Effiong",
      title: "Head of operations, Battery alliance services ",
      avatar: "/imgs/sol1.jpeg",
      text: "Working with qodespace transformed our business. Their tech solutions streamlined our processes and boosted efficiency by 40%!",
    },
    {
      name: "Edet Effiong",
      title: "Head of operations, Battery alliance services ",
      avatar: "/imgs/sol1.jpeg",
      text: "Working with qodespace transformed our business. Their tech solutions streamlined our processes and boosted efficiency by 40%!",
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
