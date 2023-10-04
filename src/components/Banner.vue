<template>
  <div class="banner">
    <div class="banner-img">
      <img :src="img" :alt="alt" />
    </div>
    <div class="banner-text-box">
      <h1 class="banner-title">{{ title }}</h1>
      <p class="banner-description">{{ description }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    img: String,
    alt: String,
    title: String,
    description: String,
  },
};
</script>
