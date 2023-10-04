<!-- Use preprocessors via the lang attribute! e.g. <template lang="pug"> -->
<template>
  <div id="app">
    <div class="hero">
      <Sidebar :siteName="siteName" :mainNavs="mainNavs" />
      <div class="content">
        <Banner :img="banner.img" :alt="banner.alt" :title="banner.title" :description="banner.description" />
        <Artical :articals="articals" />
      </div>
    </div>
  </div>
</template>

<script>
import Sidebar from "@/components/Sidebar.vue";
import Banner from "@/components/Banner.vue";
import Artical from "@/components/Artical.vue";
export default {
  components: {
    Sidebar,
    Banner,
    Artical,
  },
  data() {
    return {
      siteName: "白頭翁不吃小米",
      banner: {
        title: "白頭翁\n(Chinese\nbulbul)",
        description: "又名白頭鵯。以果實、昆蟲為主食，無法消化小米、穀類。平均壽命約 8~10 年。",
        img: "https://i.postimg.cc/Vs0mDmpH/banner.jpg",
        alt: "banner",
      },
      mainNavs: [
        { text: "白頭翁的特性", href: "#feature" },
        { text: "白頭翁的故事", href: "#story" },
        { text: "白頭翁的美照", href: "#photo" },
        { text: "白頭翁的危機", href: "#crisis" },
      ],
      articals: [
        {
          title: "外觀",
          description: "白頭鵯體長約17到22公分，額至頭頂純黑色而富有光澤，兩眼上方至後枕白色，形成一白色枕環。耳羽後部有一白斑，此白環與白斑在黑色的頭部均極為醒目，老鳥的枕羽(後頭部)更潔白，所以又叫「白頭翁」。",
        },
        {
          title: "棲地",
          description: "白頭翁和麻雀、綠繡眼合稱「城市三寶」，常成群出現在平原區灌木叢、丘陵樹林地帶，以及校園、公園、庭院、行道中的各種高高的電線與樹上。",
        },
        {
          title: "食性",
          description: "以果樹的漿果和種子為主食，並時常飛入果園偷吃果實，還會吃嫩葉嫩芽，尤其是胡蝶蘭的嫩葉嫩芽葉，偶爾啄食昆蟲。",
        },
      ],
    };
  },
};
</script>

<!-- Use preprocessors via the lang attribute! e.g. <style lang="scss"> -->
<style lang="scss">
$color-primary: #aa6666;

* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

html {
  font-size: 62.5%;
  overflow-x: hidden;
}

body {
  font-family: Noto Sans, sans-serif;
  line-height: 1;
  font-weight: 400;
  color: #000;
  overflow-x: hidden;
}

.hero {
  display: flex;
  max-width: 144rem;
  margin: 0 auto;
  position: relative;
}
.sidebar {
  position: relative;
  flex: 30;
  height: 100rem;
  background-color: #fff;
  box-shadow: 0 4px 4px rgba(0, 0, 0, 0.25);
  z-index: 1;
}

.content {
  flex: 70;
  height: 100rem;
}

.nav-title {
  text-align: center;
  margin: 0;
  padding: 7.8rem 0;
}

.mobile-nav-title {
  display: none;
}

.btn-mobile-nav {
  border: none;
  background: none;
  cursor: pointer;
}

.siteName {
  font-size: 3rem;
  font-weight: 700;
}

.main-nav-list {
  text-align: center;
  list-style: none;
  font-size: 1.8rem;
  padding: 0;
  margin: 0;
}

.main-nav-list li {
  display: inline-block;
  width: 100%;
  margin-bottom: 2rem;
}

.main-nav-link {
  border-bottom: 2px solid transparent;
}

.main-nav-link.active {
  color: $color-primary !important;
  border-bottom: 2px solid $color-primary;
}

.main-nav-link:link,
.main-nav-link:visited {
  display: inline-block;
  color: inherit;
  text-decoration: none;
  transition: all 0.3s;
}

.main-nav-link:hover,
.main-nav-link:active {
  color: $color-primary;
  border-bottom: 2px solid $color-primary;
}

.banner {
  width: 100%;
  height: 64rem;
  color: #fff;
  position: relative;
}

.banner-img {
  width: 100%;
  height: 100%;
  overflow: hidden;
}

.banner-img img {
  width: 100%;
  height: 100%;
  -o-object-fit: cover;
  object-fit: cover;
  -o-object-position: center center;
  object-position: center center;
  transform: translate(-15%, -5%) scale(1.5);
}

.banner-text-box {
  text-align: right;
  position: absolute;
  bottom: 3.685rem;
  right: 4.475rem;
}
.banner-title {
  margin: 0 0 4px 0;
  font-size: 4.8rem;
  font-weight: 700;
}

.banner-description {
  margin: 0;
  font-size: 1.8rem;
}

.artical {
  width: 100%;
  height: 36rem;
  padding: 5.815rem 0 7.2rem 0;
  background-color: #dcccbc;
}

.row {
  margin: 0 5rem;
  display: flex;
  -moz-column-gap: 7.5rem;
  column-gap: 7.5rem;
  justify-content: space-around;
  flex-wrap: nowrap;
}

.col {
  flex: 1;
  box-sizing: border-box;
}

.col-4 {
  flex-basis: calc(33.33% - 10rem);
}

.artical-text-box {
  height: 100%;
  display: flex;
  margin: auto;
}

.artical-title {
  font-size: 3.6rem;
  margin: 0;
}

.artical-description {
  height: 100%;
  margin: 0;
  padding-left: 3.784rem;
  font-size: 1.6rem;
  scrollbar-gutter: stable;
}

.inlineTitle {
  position: relative;
}

.icon {
  position: absolute;
  bottom: 0;
  right: 0;
  transform: translate(50%, 50%);
  background: $color-primary;
  opacity: 0.6;
  border-radius: 50%;
  width: 2.5rem;
  height: 2.5rem;
}

.icon::before {
  content: "";
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background: #dcccbc;
  border-radius: 50%;
  width: 1rem;
  height: 1rem;
}

.menu {
  width: 5rem;
  height: 5rem;
  display: flex;
  justify-content: center;
  align-items: center;
}

.menu-icon {
  width: 30px;
  height: 24px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  cursor: pointer;
}

.menu-icon div {
  width: 100%;
  height: 4px;
  background-color: #000;
  transition: all 0.3s ease-in-out;
}

.menu-icon div:nth-child(2) {
  width: 50%;
}

.menu-icon.is-active div:nth-child(2) {
  opacity: 0;
}

.menu-icon.is-active div:nth-child(1) {
  transform: translateY(10px) rotate(45deg);
}

.menu-icon.is-active div:nth-child(3) {
  transform: translateY(-10px) rotate(-45deg);
}

.logo {
  position: absolute;
  top: 5%;
  right: 0;
  transform: translateX(50%);
  width: 100px;
  height: 100px;
  background-color: #fff;
  border-radius: 50%;
  box-shadow: 0 0 6px rgba(0, 0, 0, 0.25);
  z-index: 1;
}

.bird {
  position: absolute;
  left: 50%;
  top: 50%;
  width: 100px;
  height: 80px;
  background-color: white;
  border-radius: 50%;
  transform: translate(-48%, -53%) scale(0.6);
}

.bird-chin {
  position: absolute;
  left: 0;
  bottom: 0;
  width: 50px;
  height: 10px;
  background-color: #000;
}

.bird-chin::before {
  content: "";
  position: absolute;
  left: 50px;
  bottom: 0;
  width: 30px;
  height: 20px;
  background-color: black;
  border-radius: 100% 0% 100% 0% / 0% 0% 100% 100%;
}

.bird-chin::after {
  content: "";
  position: absolute;
  left: 50px;
  bottom: 10px;
  width: 32px;
  height: 20px;
  background-color: white;
  border-radius: 100% 0% 100% 0% / 0% 0% 100% 100%;
}

.bird-eye {
  position: absolute;
  left: 50px;
  bottom: 30px;
  width: 15px;
  height: 15px;
  border-radius: 50%;
  background-color: black;
}

.bird-head {
  position: absolute;
  left: 0;
  bottom: 30px;
  width: 80px;
  height: 40px;
  background-color: black;
  transform: rotate(-20deg);
  border-radius: 50%;
}

.bird-head::before {
  content: "";
  position: absolute;
  left: 0;
  bottom: -10px;
  width: 80px;
  height: 40px;
  background-color: #fff;
  transform: rotate(10deg);
  border-radius: 50%;
}

.bird-mouth {
  position: absolute;
  left: 80px;
  bottom: 35px;
  width: 20px;
  height: 15px;
  border-radius: 0% 100% 100% 0% / 0% 100% 0% 100%;
  transform: rotate(-10deg);
  background-color: black;
}

@media (max-width: 1200px) {
  .hero {
    flex-direction: column;
  }
  .sidebar {
    height: auto;
  }
  .content .banner {
    height: 60rem;
  }
  .content .artical {
    height: auto;
  }

  .sidebar .logo {
    position: relative;
    transform: none;
    width: 5rem;
    height: 5rem;
  }
  .sidebar .bird {
    left: 50%;
    top: 50%;
    transform: translate(-48%, -52%) scale(0.3);
  }
  .main-nav {
    display: none;
  }
  .sidebar.nav-open .main-nav {
    display: block;
  }
  .nav-title {
    display: none;
  }
  .sidebar .mobile-nav-title {
    display: flex;
    align-items: center;
    justify-content: space-around;
    padding: 3rem 0;
  }
}
@media (max-width: 944px) {
  .row {
    flex-direction: column;
    row-gap: 5rem;
  }
}
@media (max-width: 711px) {
  .sidebar {
    height: 30rem;
  }
  .content .banner {
    height: 30rem;
  }
  .content .artical {
    height: auto;
  }
  .sidebar .nav-title {
    padding: 3rem 0 3.4rem 0;
  }
  .banner .banner-text-box {
    position: absolute;
    bottom: 2.4rem;
    right: 2.2rem;
  }
  .banner .banner-title {
    white-space: pre-line;
  }
  .banner .banner-description {
    text-wrap: balance;
  }
  .mobile-nav-title .siteName {
    font-size: 2rem;
  }
  .menu .menu-icon {
    width: 24px;
    height: 20px;
  }
  .menu .menu-icon.is-active div:nth-child(1) {
    transform: translateY(6px) rotate(45deg);
  }
}
</style>
