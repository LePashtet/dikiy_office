<template>
  <div id="app">
    <!--    <CInfiniteScroll :items="items">-->
    <!--      <template #default="{ item, active }">-->
    <!--        <CInfiniteScrollItem :item="item" :active="active">-->
    <!--          <component :is="item"></component>-->
    <!--        </CInfiniteScrollItem>-->
    <!--      </template>-->
    <!--    </CInfiniteScroll>-->
    <frame1></frame1>
    <frame2 id="frame2"></frame2>
    <frame3></frame3>
    <frame4></frame4>
    <frame5></frame5>
    <frame52></frame52>
    <frame53></frame53>
    <frame54></frame54>
    <frame55></frame55>
    <frame6></frame6>
    <frame7></frame7>
    <frame8></frame8>
    <frame9 id="frame9"></frame9>
    <frame10></frame10>
    <frame11></frame11>
    <my-footer id="my-footer"></my-footer>
  </div>
</template>

<script>
// import lazyLoadComponent from "@/utils/lazy-load-component";
// import { InfiniteScroll, InfiniteScrollItem } from "@vue-cdk/infinite-scroll";
// import "@vue-cdk/infinite-scroll/style/index.css";

export default {
  name: "App",
  components: {
    frame1: () => import("@/components/Frame1.vue"),
    frame2: () => import("@/components/Frame2.vue"),
    frame3: () => import("@/components/Frame3.vue"),
    frame4: () => import("@/components/Frame4.vue"),
    frame5: () => import("@/components/Frame5.vue"),
    frame52: () => import("@/components/Frame5.2.vue"),
    frame53: () => import("@/components/Frame5.3.vue"),
    frame54: () => import("@/components/Frame5.4.vue"),
    frame55: () => import("@/components/Frame5.5.vue"),
    frame6: () => import("@/components/Frame6.vue"),
    frame7: () => import("@/components/Frame7.vue"),
    frame8: () => import("@/components/Frame8.vue"),
    frame9: () => import("@/components/Frame9.vue"),
    frame10: () => import("@/components/Frame10.vue"),
    frame11: () => import("@/components/Frame11.vue"),
    myFooter: () => import("@/components/Footer.vue")
    // InfiniteScroll,
    // InfiniteScrollItem
    // HelloWorld2: lazyLoadComponent({
    //   componentFactory: () => import("@/components/HelloWorld2.vue")
    // })
  },
  data: () => ({
    items: [
      "frame1",
      "frame2",
      "frame3",
      "frame4",
      "frame5",
      "frame52",
      "frame53",
      "frame54",
      "frame55",
      "frame6",
      "frame7",
      "frame8",
      "frame9",
      "frame10",
      "frame11",
      "my-footer"
    ]
  })
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600;800&display=swap");
* {
  margin: 0;
  padding: 0;
}

#app {
  font-family: Montserrat, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  -webkit-touch-callout: none; /* iOS Safari */
  -webkit-user-select: none; /* Safari */
  -khtml-user-select: none; /* Konqueror HTML */
  -moz-user-select: none; /* Old versions of Firefox */
  -ms-user-select: none; /* Internet Explorer/Edge */
  user-select: none;
}

h3 {
  font-weight: 600;
  font-size: 16px;
  line-height: 20px;
  letter-spacing: 0.05em;
  text-transform: uppercase;
  color: #ff7e00;
  text-align: start;
}
.hooper-track {
  transition: all 5000ms linear 0s !important;
}
.team__profiles .hooper-track,
.feedback__profiles .hooper-track,
.slideshow__profiles .hooper-track {
  transition: all 800ms ease-in-out 0s !important;
}
.mobile {
  display: none;
  @media (max-width: 1023px) {
    display: block;
  }
}
</style>
