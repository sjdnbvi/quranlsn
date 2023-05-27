<template>
  <q-layout view="hHh lpR fFf">
    <q-header reveal elevated class="bg-primary text-white" height-hint="98">
      <div class="q-pa-md">
        <div class="row">
          <div class="col">
            <q-toolbar>
              <q-btn
                class="mobile-only"
                dense
                flat
                round
                icon="menu"
                @click="toggleLeftDrawer"
              />
              <img src="../../public/icons/logo.png" />
            </q-toolbar>
          </div>

          <div class="col-10 desktop-only">
            <q-tabs>
              <q-route-tab to="/about" label="درباره کانون" />
              <q-route-tab to="/contact" label="ارتباط با کانون" />
              <q-route-tab to="/works" label="آثار" />
              <q-route-tab to="/news" label="اخبار و رویدادها" />
            </q-tabs>
          </div>

          <div class="col desktop-only">
            <q-btn color="white" text-color="black" label="ورود آنلاین" />
          </div>
        </div>
      </div>
    </q-header>
    <q-drawer
      class="mobile-only"
      v-model="rightDrawerOpen"
      side="right"
      bordered
    >
      <!-- drawer content -->

      <q-item>1</q-item>
      <q-item>2</q-item>
      <q-tabs>
        <q-item to="/about" label="درباره کانون" />
        <q-item to="/contact" label="ارتباط با کانون" />
        <q-item to="/works" label="آثار" />
        <q-item to="/news" label="اخبار و رویدادها" />
      </q-tabs>
    </q-drawer>
    <q-page-container>
      <!-- <router-view /> -->
      <q-page>
        <div class="q-pa-md">
          <q-carousel
            class="desktop-only"
            animated
            v-model="slide"
            navigation
            infinite
            :autoplay="autoplay"
            arrows
            transition-prev="slide-right"
            transition-next="slide-left"
            @mouseenter="autoplay = false"
            @mouseleave="autoplay = true"
          >
            <q-carousel-slide
              :name="1"
              img-src="https://cdn.quasar.dev/img/mountains.jpg"
            />
            <q-carousel-slide
              :name="2"
              img-src="https://cdn.quasar.dev/img/parallax1.jpg"
            />
            <q-carousel-slide
              :name="3"
              img-src="https://cdn.quasar.dev/img/parallax2.jpg"
            />
            <q-carousel-slide
              :name="4"
              img-src="https://cdn.quasar.dev/img/quasar.jpg"
            />
          </q-carousel>
        </div>
      </q-page>
    </q-page-container>

    <q-footer elevated class="bg-grey-8 text-white">
      <q-tabs
        no-caps
        active-color="primary"
        indicator-color="transparent"
        class="text-grey-8"
        v-model="tab"
      >
        <q-tab name="images" label="Images" />
        <q-tab name="videos" label="Videos" />
        <q-tab name="articles" label="Articles" />
      </q-tabs>

      <!-- <q-toolbar>
        <q-toolbar-title>
        </q-toolbar-title>
        <div class="text-center">کلیه حقوق برای کانون زبان قرآن محفوظ است.</div>
      </q-toolbar> -->
    </q-footer>
  </q-layout>
  <!-- <q-ajax-bar hijack-filter="myfilter"></q-ajax-bar> -->
</template>


<script>
import { ref } from "vue";

export default {
  setup() {
    const rightDrawerOpen = ref(false);
    return {
      slide: ref(1),
      rightDrawerOpen,
      toggleLeftDrawer() {
        rightDrawerOpen.value = !rightDrawerOpen.value;
      },
    };
  },
};
</script>

