<script setup>
import 'vue3-carousel/carousel.css'
import { Carousel, Slide, Pagination, Navigation } from 'vue3-carousel'
import { ref } from 'vue'

const currentSlide = ref(0)

const slideTo = (nextSlide) => (currentSlide.value = nextSlide)

const galleryConfig = {
  itemsToShow: 1,
  wrapAround: true,
  slideEffect: 'fade',
  mouseDrag: false,
  touchDrag: false,
  height: 320,
}

const thumbnailsConfig = {
  height: 80,
  itemsToShow: 6,
  wrapAround: true,
  touchDrag: false,
  gap: 30,
}

const images = [
 {
  id: 1,
  url: `https://raw.githubusercontent.com/SeanCyan/Portfolio/refs/heads/master/img/OSR/aaOSR.png`
 },
 {
  id: 2,
  url: `https://raw.githubusercontent.com/SeanCyan/Portfolio/refs/heads/master/img/OSR/bonucciOSR.png`
 },
 {
  id: 3,
  url: `https://raw.githubusercontent.com/SeanCyan/Portfolio/refs/heads/master/img/OSR/kenyaOSR.png`
 },
 {
  id: 4,
  url: `https://raw.githubusercontent.com/SeanCyan/Portfolio/refs/heads/master/img/OSR/loccitaneOSR.png`
 },
 {
  id: 5,
  url: `https://raw.githubusercontent.com/SeanCyan/Portfolio/refs/heads/master/img/OSR/maisonOSR.png`
 },
 {
  id: 6,
  url: `https://raw.githubusercontent.com/SeanCyan/Portfolio/refs/heads/master/img/OSR/palaceOSR.png`
 },
 {
  id: 7,
  url: `https://raw.githubusercontent.com/SeanCyan/Portfolio/refs/heads/master/img/OSR/sisleyOSR.png`
 },
 {
  id: 8,
  url: `https://raw.githubusercontent.com/SeanCyan/Portfolio/refs/heads/master/img/OSR/doublefOSR.png`
 },
 {
  id: 9,
  url: `https://raw.githubusercontent.com/SeanCyan/Portfolio/refs/heads/master/img/OSR/eeOSR.png`
 }
]


console.log(images);
</script>

<template>
  <Carousel id="gallery" v-bind="galleryConfig" v-model="currentSlide">
    <Slide v-for="image in images" :key="image.id">
      <img :src="image.url" alt="Gallery Image" class="gallery-image" />
    </Slide>
  </Carousel>

  <Carousel id="thumbnails" v-bind="thumbnailsConfig" v-model="currentSlide">
    <Slide v-for="image in images" :key="image.id">
      <template #default="{ currentIndex, isActive }">
        <div
          :class="['thumbnail', { 'is-active': isActive }]"
          @click="slideTo(currentIndex)"
        >
          <img :src="image.url" alt="Thumbnail Image" class="thumbnail-image" />
        </div>
      </template>
    </Slide>

    <template #addons>
      <Navigation />
    </template>
  </Carousel>
</template>

<style>
:root {
  background-color: #cccccc;
}
#gallery {
  height:auto;
}
.carousel {
  --vc-nav-background: rgba(255, 255, 255, 0.7);
  --vc-nav-border-radius: 100%;
  
}

img {
  border-radius: 8px;
  width: 100%;
  height: auto;
  object-fit: contain;
}



.gallery-image {
  border-radius: 16px;
  width: auto;
  height: auto;
  -webkit-box-shadow: 0px 0px 32px -8px rgba(0,0,0,0.2);
-moz-box-shadow: 0px 0px 32px -8px rgba(0,0,0,0.2);
box-shadow: 0px 0px 32px -8px rgba(0,0,0,0.2);
margin:25px auto;
}

#thumbnails {
  margin-top: 10px;
  width: auto;
  height: auto;

}

.thumbnail {
  height: auto;
  width: 100%;
  cursor: pointer;
  opacity: 0.6;
  transition: opacity 0.3s ease-in-out;
}

.thumbnail.is-active,
.thumbnail:hover {
  opacity: 1;
}
.carousel__next,
.carousel__prev {
 background: rgba(0, 0, 0, 0.3);
 border-radius: 50%;
 width: 40px;
 height: 40px;
 color: white;
 margin: 0 10px;
}
@media (max-width: 1024px) {
  .gallery-image {
  border-radius: 16px;
  width: 90vw;
  height: auto;
  -webkit-box-shadow: 0px 0px 32px -8px rgba(0,0,0,0.2);
-moz-box-shadow: 0px 0px 32px -8px rgba(0,0,0,0.2);
box-shadow: 0px 0px 32px -8px rgba(0,0,0,0.2);
margin:25px auto;
}

}
</style>
