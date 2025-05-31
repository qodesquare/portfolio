<template>
  <div>
    <Carousel
      :plugins="[autoplay]"
      @init-api="setApi"
      :opts="{
        loop: true,
      }"
    >
      <CarouselContent class="-ml-4">
        <CarouselItem
          class="pl-4 md:basis-2/3 lg:basis-2/4 xl:basis-2/5 2xl:basis-2/6"
          v-for="(testimonial, index) in testimonials"
          :key="testimonial.name"
        >
          <TestimonialCard
            class="col-span-1 transition delay-150 duration-300 ease-in-out"
            :class="{
              'scale-90': index !== currentSlide,
            }"
            :name="testimonial.name"
            :title="testimonial.title"
            :avatar="testimonial.avatar"
          >
            {{ testimonial.text }}
          </TestimonialCard>
        </CarouselItem>
      </CarouselContent>
    </Carousel>
    <div class="flex justify-center mt-3 space-x-2">
      <button
        v-for="(slide, index) in totalSlides"
        :key="index"
        @click="onThumbClick(index)"
        :class="{
          'h-3 rounded-full transition-all duration-1000': true,
          'bg-black w-16': currentSlide === index,
          'bg-[#F2F2F2] w-3': currentSlide !== index,
        }"
      ></button>
    </div>
  </div>
</template>

<script setup lang="ts">
  import TestimonialCard from "@/components/templates/landing/TestimonialCard.vue";
  import Autoplay from "embla-carousel-autoplay";
  import { ref } from "vue";
  import { watchOnce } from "@vueuse/core";
  import type { CarouselApi } from "@/components/ui/carousel";
  import type { Testimonial } from "@/types/testimonial";

  const api = ref<CarouselApi>();
  const totalSlides = ref(0);
  const currentSlide = ref(0);

  function setApi(val: CarouselApi) {
    api.value = val;
  }

  watchOnce(api, (api) => {
    if (!api) return;

    totalSlides.value = api.scrollSnapList().length;
    currentSlide.value = api.selectedScrollSnap();

    api.on("select", () => {
      currentSlide.value = api.selectedScrollSnap();
      // console.log(
      //   currentSlide.value,
      //   totalSlides.value,
      //   api.selectedScrollSnap()
      // );
    });
  });

  function onThumbClick(index: number) {
    if (!api.value) return;

    api.value.scrollTo(index);
  }

  const autoplay = Autoplay({
    delay: 20000,
    // duration: 1000,
    stopOnMouseEnter: true,
    stopOnInteraction: false,
  });

  defineProps<{
    testimonials: Testimonial[];
  }>();
</script>

<style scoped></style>
