<script>
export default {
  props: ["img"],
};
</script>

<template>
  <div class="card column is-3">
    <div class="card-image">
      <a :href="img.url" :download="encodeURIComponent(img.title) + '.jpg'">
        <figure class="image is-4by3">
          <img :src="img.url" :alt="img.title" />
        </figure>
      </a>
    </div>

    <div class="card-content">
      <h3 class="title is-3">{{ img.title }}</h3>
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
      <a href="#" class="card-footer-item">Edit</a>
      <a href="#" class="card-footer-item">Delete</a>
    </footer>
  </div>
</template>
