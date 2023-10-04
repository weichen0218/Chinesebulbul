<template>
  <div class="artical">
    <div class="row">
      <div class="col col-4" v-for="(artical, index) in articals" :key="index">
        <div class="artical-text-box">
          <h2 class="artical-title">
            <div class="inlineTitle">
              {{ artical.title }}
              <div class="icon"></div>
            </div>
          </h2>
          <p class="artical-description">{{ artical.description }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    articals: Array,
  },
};
</script>
