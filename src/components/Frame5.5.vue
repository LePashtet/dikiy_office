<template>
  <section class="slideshow">
    <h3>
      как<br />
      проходят<br />
      игры
    </h3>
    <div class="slideshow__slider-wrp">
      <hooper
        ref="carousel"
        :style="{ height: options.height }"
        :items-to-show="options.itemsToShow"
        :center-mode="true"
        :touchDrag="false"
        :mouseDrag="false"
        :wheelControl="false"
        class="slideshow__profiles"
      >
        <slide class="slideshow-slide">
          <img src="@/assets/slide1.png" alt="Slide" />
        </slide>
        <slide class="slideshow-slide">
          <img src="@/assets/slide2.png" alt="Slide" />
        </slide>
        <slide class="slideshow-slide">
          <img src="@/assets/slide3.png" alt="Slide" />
        </slide>
      </hooper>
      <div class="arrows">
        <img
          src="@/assets/arrow.svg"
          style="transform: rotateZ(90deg)"
          alt="Prev"
          @click="slidePrev"
        />
        <img
          src="@/assets/arrow.svg"
          style="transform: rotateZ(-90deg)"
          alt="Next"
          @click="slideNext"
        />
      </div>
    </div>
  </section>
</template>

<script>
import { Hooper, Slide } from "hooper";
import "hooper/dist/hooper.css";
export default {
  name: "Frame5.5",
  components: {
    Hooper,
    Slide
  },
  data: () => ({
    options: {
      height: "max-content",
      centerMode: true,
      itemsToShow: 2.5
    }
  }),
  methods: {
    slidePrev() {
      this.$refs.carousel.slidePrev();
    },
    slideNext() {
      this.$refs.carousel.slideNext();
    },
    myEventHandler(e) {
      if (e.target.outerWidth < 1024) {
        this.options.itemsToShow = 1;
      } else {
        this.options.itemsToShow = 2.5;
      }
      this.$forceUpdate();
    }
  },
  created() {
    if (window.innerWidth < 1024) {
      this.options.itemsToShow = 1;
    } else {
      this.options.itemsToShow = 2.5;
    }
    this.$forceUpdate();

    window.addEventListener("resize", this.myEventHandler);
  },
  destroyed() {
    window.removeEventListener("resize", this.myEventHandler);
  }
};
</script>

<style scoped lang="scss">
p {
  text-align: start;
}

.slideshow {
  height: 100%;
  min-height: 100vh;
  box-sizing: border-box;
  padding: 7% 0 3%;
  position: relative;
  background: #343434;
  h3 {
    padding-left: 200px;
    margin-bottom: 15%;
    @media (max-width: 1023px) {
      padding-left: 20px;
    }
  }

  &__slider-wrp {
    position: relative;
  }
  &-slide {
    display: flex;
    text-align: start;
    justify-content: space-between;
    height: max-content;
    width: 50%;
    div {
      margin: 0 auto;
      position: relative;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      max-width: 400px;
      width: 90%;
      &:nth-child(1) {
        padding: 100px 0 40px 0;
      }

      img {
        max-width: 375px;
        margin: 0 auto;
      }
    }
    @media (max-width: 1023px) {
      flex-direction: column;
      div {
        img {
          width: 200px;
        }
        &:nth-child(2) {
          padding: 50px 0 20px 0;
        }
      }
    }
  }
  .arrows {
    display: flex;
    justify-content: space-between;
    padding: 0 5%;
    position: absolute;
    width: 90%;
    bottom: -15%;
  }

  @media (max-width: 1023px) {
    padding: 7% 20px 3%;
    min-height: 70vh;
    &-slide {
      div {
        &:nth-child(1) {
          padding: 50px 0 40px 0;
        }
      }
    }
  }
}
</style>
