<script>
import bannerMobile from "../assets/images/image-hero-mobile.png";
import bannerDesktop from "../assets/images/image-hero-mobile.png";

import clientAudiophile from "../assets/images/client-audiophile.svg";
import clientDatabiz from "../assets/images/client-databiz.svg";
import clientMaker from "../assets/images/client-maker.svg";
import clientMeet from "../assets/images/client-meet.svg";

export default {
  data: function () {
    return {
      bannerMobile,
      bannerDesktop,
      clientLogos: [
        clientAudiophile,
        clientDatabiz,
        clientMaker,
        clientMeet,
      ]
    };
  },
};
</script>

<template>
  <section class="intro-section">
    <div class="banner-content">
      <img class="banner-mobile" :src="bannerMobile" alt="banner img">
      <img class="banner-desktop" :src="bannerDesktop" alt="banner img">
    </div>

    <div class="intro-info">
      <h1>Make remote work</h1>
      <p>
        Get your team in sync, no matter your location. Streamline processes,
        create team rituals, and watch productivity soar.
      </p>
      <button>Learn more</button>

      <div class="client-logo-content">
        <img :key="client" v-for="client in clientLogos" :src="client" alt="client logo">
      </div>
    </div>
  </section>
</template>

<style>
.banner-desktop {
  display: none;
}
</style>
