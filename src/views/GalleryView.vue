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
  <div class="columns">
    <div class="column has-text-centered">
      <h1 class="title">Gallery</h1>
      <br />
    </div>
  </div>
  <div class="row columns is-multiline">
    <div v-for="(img, i) in images" :key="i" class="card column is-3">
      <div class="card-image">
        <figure class="image is-4by3">
          <img :src="img.url" :alt="img.title" />
        </figure>
      </div>
      <div class="card-header">
        <p class="card-header-title">
          {{ img.title }}
        </p>
      </div>
      <div class="card-content">
        <div class="content">
          <time :datetime="img.timestamp.toISOString()">{{
            img.timestamp.toLocaleString("de-DE", {
              weekday: "long",
              year: "numeric",
              month: "long",
              day: "numeric",
            })
          }}</time>
        </div>
      </div>
      <footer class="card-footer">
        <a href="#" class="card-footer-item">Download</a>
        <a href="#" class="card-footer-item">Edit</a>
        <a href="#" class="card-footer-item">Delete</a>
      </footer>
    </div>
  </div>
</template>
