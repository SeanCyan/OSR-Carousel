<script setup>
import 'vue3-carousel/carousel.css'
import { Carousel, Slide, Pagination, Navigation } from 'vue3-carousel'

const carouselConfig = {
  dir: 'ttb',
  wrapAround: true,
  itemsToShow:1,
  snapAlign: 'center',
  height: '90vh',
  gap: 5,
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
  <Carousel v-bind="carouselConfig">
    <Slide v-for="img in images" :key="img.id">
      <img :src="img.url" />
    </Slide>

    <template #addons>
      <Navigation />
      <Pagination />
    </template>
  </Carousel>
</template>

<style>
:root {
  background-color: #242424;
}

.carousel {
  --vc-pgn-background-color: rgba(255, 255, 255, 0.7);
  --vc-pgn-active-color: rgba(255, 255, 255, 1);
  --vc-nav-background: rgba(255, 255, 255, 0.7);
  --vc-nav-border-radius: 100%;
  width:100vw;
margin: 25px auto 10px;
}

.carousel__slide {
  border-radius: 20px;
  overflow: hidden;
}

img {
  border-radius:20px;
  width: 70vw;
  height: auto;
  object-fit: contain;
  -webkit-box-shadow: 0px 0px 32px -8px rgba(0,0,0,0.2);
-moz-box-shadow: 0px 0px 32px -8px rgba(0,0,0,0.2);
box-shadow: 0px 0px 32px -8px rgba(0,0,0,0.2);
}
</style>
