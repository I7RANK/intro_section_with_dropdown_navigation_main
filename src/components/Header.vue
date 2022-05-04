<script>
import menuButtonImg from "../assets/images/logo.svg";
import iconMenu from "../assets/images/icon-menu.svg";
import iconCloseMenu from "../assets/images/icon-close-menu.svg";

export default {
  data: function () {
    return {
      menuButtonImg,
      iconMenu,
      iconCloseMenu,
      toggleMainMenu: true,
    };
  },
  methods: {
    handleToggleMainMenu() {
      this.toggleMainMenu = !this.toggleMainMenu;
    },
  },
};
</script>

<template>
  <header>
    <div class="logo">
      <img src="../assets/images/logo.svg" alt="main logo" />
    </div>
    <div class="nav-bar"></div>
    <div class="dropdown-menu">
      <img v-if="toggleMainMenu === true" :src="iconMenu" alt="menu button" @click="this.handleToggleMainMenu"/>
      <img v-else :src="iconCloseMenu" alt="menu button" @click="this.handleToggleMainMenu"/>
    </div>
  </header>
</template>

<style>
.dropdown-menu img {
  transition: display .3 ease;
}
</style>
