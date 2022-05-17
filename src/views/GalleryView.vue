<script setup lang="ts">
import GalleryItem from "@/components/GalleryItem.vue";

interface Image {
  url: string;
  timestamp: Date;
  title: string;
}

const images: Image[] = [
  {
    url: "https://i.ytimg.com/vi/Ibcaejm1E3c/maxresdefault.jpg",
    timestamp: new Date(),
    title: "Test Image",
  },
  {
    url: "https://i.imgflip.com/3bh4ta.jpg",
    timestamp: new Date(),
    title: "Joe",
  },
  {
    url: "https://i.ytimg.com/vi/k6g4ofr3fEw/hqdefault.jpg",
    timestamp: new Date(),
    title: "SUBAUWU",
  },
];
</script>

<template>
  <div class="container">
    <div class="section">
      <div class="columns">
        <div class="column has-text-centered">
          <h1 class="title">Gallery</h1>
          <br />
        </div>
      </div>
      <div class="row container">
        <div class="columns">
          <GalleryItem v-for="(img, i) in images" :key="i" :img="img" />
        </div>
      </div>
    </div>
  </div>
</template>
