<template>
  <v-layout class="mx-auto">
    <v-row no-gutters style="width: 99vw;">
      <v-col cols="12" class="half-section">
        <v-img class="main-header-image" src="/img/homies-blur.jpg" aspect-ratio="1">
          <v-row
            class="main-header-text fill-height text-center"
            align="center"
          >
            <v-col>
              <h5 class="main-header-text-top">We Are</h5>
              <div class="mx-auto text-center d-flex justify-center">
                <vue-typed-js
                  class="main-header-text-bottom"
                  :loop="true"
                  :typeSpeed="100"
                  :backSpeed="100"
                  :shuffle="false"
                  :contentType="'null'"
                  :strings="[
                    'Friend',
                    'Family',
                    'Enemy',
                    'Gang',
                    'Besties',
                    'Homies ^5000'
                  ]"
                >
                  <span class="typing"></span>
                </vue-typed-js>
              </div>
            </v-col>
          </v-row>
        </v-img>
      </v-col>
      <v-col cols="12" class="section about-us">
        <v-row>
          <v-col cols="12">
            <h3 class="section-title">About Us</h3>
          </v-col>
          <v-col cols="12">
            <v-img class="section-image" src="/img/homies.jpg" height="200px" />
          </v-col>
          <v-col cols="12">
            <v-tabs
              grow
              background-color="#EEA990"
              color="#66545E"
              v-model="language"
            >
              <v-tab>EN</v-tab>
              <v-tab>ID</v-tab>
            </v-tabs>
            <v-tabs-items v-model="language">
              <v-tab-item>
                <v-row no-gutters>
                  <v-col class="about-us-description">
                    <p>
                      Starting off from borrowing a keyboard, hanging out at
                      Brian's house, then things are getting serious. We did
                      crazy stuffs like going home without wearing any clothes,
                      giving an updates everytime we go to toilet, sleep overs
                      at one of us' house for months, till' now. We have our own
                      website.
                    </p>
                  </v-col>
                </v-row>
              </v-tab-item>
              <v-tab-item>
                <v-row no-gutters>
                  <v-col class="about-us-description">
                    <p>
                      Berawal dari meminjam keyboard, main bareng ke rumah Brian
                      lalu berlanjut ke pulang serentak tanpa baju, membuat grup
                      whatsapp, mengabari saat buang air, menginap di rumah
                      salah satu dari kami berbulan - bulan, hingga kini. Kami
                      memiliki situs khusus untuk kami.
                    </p>
                  </v-col>
                </v-row>
              </v-tab-item>
            </v-tabs-items>
          </v-col>
        </v-row>
      </v-col>
      <v-col cols="12" class="full-section section">
        <v-row>
          <v-col cols="12">
            <h3 class="section-title">Gallery</h3>
          </v-col>
          <v-col cols="12">
            <v-carousel
              hide-delimiters
              cycle
              interval="3000"
              class="gallery-images"
              height="350"
            >
              <v-carousel-item
                v-ripple
                v-for="(photos, index) in images"
                :key="index"
                :src="'/img/gallery/' + photos.src"
              />
            </v-carousel>
          </v-col>
        </v-row>
      </v-col>
    </v-row>
    <v-footer absolute class="footer">
      <v-row>
        <v-col>
          <h3>
            &copy; H O M I E S |
            <a class="grey--text" href="mailto:homies@comebackho.me">homies@comebackho.me</a>
          </h3>
        </v-col>
      </v-row>
    </v-footer>
  </v-layout>
</template>

<script>
import photos from "~/assets/images.js";
export default {
  data() {
    return {
      language: null,
      images: photos
    };
  }
  // async asyncData({ $content }) {
  //   const page = await $content("hello").fetch();
  //   return {
  //     page
  //   };
  // }
};
</script>

<style lang="sass" scoped>
.half-section
  height: 50vh
.full-section
  height: 100vh
.main-header-image
  height: 100%
.main-header-text
  color: #F6E0B5
.main-header-text-top
  font-family: 'Caveat', cursive
  font-size: 2rem
.main-header-text-bottom
  font-family: 'Architects Daughter', cursive
  font-size: 4rem
  align-self: center
.section
  padding: 25px
  background: #F6E0B5
.section-title
  color: #AA6F73
  border-bottom: 1px solid #AA6F73
  display: inline-block
  font-family: 'Architects Daughter', cursive
  font-size: 2rem
.section-image
  width: 100%
  border-radius: 10pt
.about-us-description
  background: #F6E0B5
  font-family: 'Architects Daughter', cursive
  color: #AA6F73
  padding: 10px
  text-align: justify
.gallery-images
  border-radius: 15pt
.footer
  color: #F6E0B5
  text-align: center
  height: 10vh
  background: #66545E
  font-family: 'Montserrat', sans-serif
*
  // border: 1px solid blue
</style>
