<template>
  <div :class="['sidebar', { 'nav-open': isNavOpen }]">
    <div class="nav-title">
      <h2 class="siteName">{{ siteName }}</h2>
      <div class="logo">
        <div class="bird">
          <div class="bird-head"></div>
          <div class="bird-eye"></div>
          <div class="bird-mouth"></div>
          <div class="bird-chin"></div>
        </div>
      </div>
    </div>
    <div class="mobile-nav-title">
      <button @click.prevent="toggleNav" class="btn-mobile-nav">
        <div class="menu">
          <div :class="['menu-icon', { 'is-active': isNavOpen }]">
            <div></div>
            <div></div>
            <div></div>
          </div>
        </div>
      </button>

      <h2 class="siteName">{{ siteName }}</h2>
      <div class="logo">
        <div class="bird">
          <div class="bird-head"></div>
          <div class="bird-eye"></div>
          <div class="bird-mouth"></div>
          <div class="bird-chin"></div>
        </div>
      </div>
    </div>

    <nav class="main-nav">
      <ul class="main-nav-list">
        <li v-for="(mainNav, index) in mainNavs" :key="index">
          <a :class="['main-nav-link', { active: index === 0 }]" :href="mainNav.href">{{ mainNav.text }}</a>
        </li>
      </ul>
    </nav>
  </div>
</template>

<script>
export default {
  name: "Sidebar",
  props: {
    siteName: String,
    mainNavs: Array,
  },
  data() {
    return {
      isNavOpen: false,
    };
  },
  methods: {
    toggleNav() {
      this.isNavOpen = !this.isNavOpen;
    },
  },
};
</script>
