<template>
  <section class="team">
    <h3>
      наша <br />
      команда
    </h3>
    <div class="team__slider-wrp">
      <hooper
        ref="carousel"
        :style="{ height: options.height }"
        :itemsToShow="options.itemsToShow"
        :touchDrag="false"
        :mouseDrag="false"
        :wheelControl="false"
        class="team__profiles"
      >
        <slide class="team-slide">
          <div><img src="@/assets/angela.png" alt="Team Photo" /></div>
          <div>
            <p>
              Тренинг формирует командный дух, и тем самым влияет на рост и
              прибыль компании. Например, теперь мы все играем в крестики-нолики
              и пьём какао по утрам. А еще всей толпой побили быбку-вахтёршу.
              Потому что у неё нет командного духа и вообще.
            </p>
            <p class="white">Анжела Топчий, коуч</p>
          </div>
        </slide>
        <slide class="team-slide">
          <div><img src="@/assets/angela.png" alt="Team Photo" /></div>
          <div>
            <p>
              Тренинг формирует командный дух, и тем самым влияет на рост и
              прибыль компании. Например, теперь мы все играем в крестики-нолики
              и пьём какао по утрам. А еще всей толпой побили быбку-вахтёршу.
              Потому что у неё нет командного духа и вообще.
            </p>
            <p class="white">Анжела Топчий, коуч</p>
          </div>
        </slide>
        <slide class="team-slide">
          <div><img src="@/assets/angela.png" alt="Team Photo" /></div>
          <div>
            <p>
              Тренинг формирует командный дух, и тем самым влияет на рост и
              прибыль компании. Например, теперь мы все играем в крестики-нолики
              и пьём какао по утрам. А еще всей толпой побили быбку-вахтёршу.
              Потому что у неё нет командного духа и вообще.
            </p>
            <p class="white">Анжела Топчий, коуч</p>
          </div>
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
    <infinite-slide-bar duration="6s" class="slide2">
      <span :key="item" v-for="item in 6" class="team-slide2">Дикий офис</span>
    </infinite-slide-bar>
  </section>
</template>

<script>
import { Hooper, Slide } from "hooper";
import "hooper/dist/hooper.css";
import InfiniteSlideBar from "vue-infinite-slide-bar";

export default {
  name: "Frame10",
  components: {
    Hooper,
    Slide,
    InfiniteSlideBar
  },
  data: () => ({
    options: {
      height: "max-content",
      itemsToShow: 1.3,
      centerMode: true
    },
    width: null
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
        this.options.itemsToShow = 2;
      }
      this.$forceUpdate();
    }
  },
  created() {
    window.addEventListener("resize", this.myEventHandler);
  },
  destroyed() {
    window.removeEventListener("resize", this.myEventHandler);
  }
};
</script>

<style scoped lang="scss">
.team {
  background: #343434;
  box-sizing: border-box;
  padding: 3% 0 80px;
  position: relative;
  min-height: 100vh;
  height: 100%;

  h3 {
    padding-left: 200px;
    margin-bottom: 7%;
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
      &:nth-child(2) {
        padding: 100px 0 40px 0;
      }

      p {
        font-weight: normal;
        font-size: 18px;
        line-height: 24px;
        letter-spacing: 0.05em;
        color: #ffffff;
      }
      .white {
        font-weight: 600;
        font-size: 22px;
        line-height: 24px;
        letter-spacing: 0.05em;
        color: #ffffff;
      }
      p:not(.white):before {
        content: "“";
        font-weight: 800;
        font-size: 300px;
        line-height: 366px;
        -webkit-text-stroke: 2px #ff7e00;
        text-stroke: 2px #ff7e00;
        box-sizing: border-box;
        color: rgba(#343434, 0);
        position: absolute;
        top: -15%;
      }
      img {
        max-width: 375px;
        margin: 0 auto;
      }
    }
    @media (max-width: 1023px) {
      flex-direction: column;
      min-height: 50vh;
      justify-content: flex-end;

      div {
        img {
          width: 200px;
        }
        &:nth-child(2) {
          padding: 50px 0 20px 0;
        }
        p {
          font-size: 14px;
          line-height: 18px;
        }
        p:not(.white):before {
          font-weight: 800;
          font-size: 150px;
          line-height: 180px;
          -webkit-text-stroke: 2px #ff7e00;
          text-stroke: 2px #ff7e00;
          top: -10%;
        }
        .white {
          font-size: 18px;
          line-height: 24px;
        }
      }
    }
  }
  .arrows {
    display: flex;
    justify-content: space-between;
    position: absolute;
    padding: 0 3%;
    width: 90%;
  }
  &-slide2 {
    font-weight: 800;
    font-size: 2rem;
    -webkit-text-stroke: 1px #ff7e00;
    text-stroke: 1px #ff7e00;
    box-sizing: border-box;
    color: rgba(#343434, 0);
    margin: 0 20px;
    @media (max-width: 1023px) {
      font-weight: 600;
      font-size: 15px;
    }
  }
  .slide2 {
    position: absolute;
    bottom: 0;
  }

  @media (max-width: 1023px) {
    min-height: 90vh;
  }
}
</style>
