<template>
  <section class="feedback">
    <h3>
      что<br />
      о нас<br />
      говорят
    </h3>
    <div class="feedback__slider-wrp">
      <hooper
        ref="carousel"
        :style="{ height: options.height }"
        :itemsToShow="options.itemsToShow"
        :touchDrag="false"
        :mouseDrag="false"
        :wheelControl="false"
        class="feedback__profiles"
      >
        <slide class="feedback-slide">
          <div>
            <p>
              Тренинг формирует командный дух, и тем самым влияет на рост и
              прибыль компании. Например, теперь мы все играем в крестики-нолики
              и пьём какао по утрам. А еще всей толпой побили быбку-вахтёршу.
              Потому что у неё нет командного духа и вообще.
            </p>
            <img class="user" src="@/assets/user_icon.png" alt="User" />
            <p class="white">Анжела Топчий, коуч</p>
          </div>
          <div><img src="@/assets/angela.png" alt="Team Photo" /></div>
        </slide>
        <slide class="feedback-slide">
          <div>
            <p>
              Тренинг формирует командный дух, и тем самым влияет на рост и
              прибыль компании. Например, теперь мы все играем в крестики-нолики
              и пьём какао по утрам. А еще всей толпой побили быбку-вахтёршу.
              Потому что у неё нет командного духа и вообще.
            </p>
            <p class="white">Анжела Топчий, коуч</p>
          </div>
          <div><img src="@/assets/angela.png" alt="Team Photo" /></div>
        </slide>
        <slide class="feedback-slide">
          <div>
            <p>
              Тренинг формирует командный дух, и тем самым влияет на рост и
              прибыль компании. Например, теперь мы все играем в крестики-нолики
              и пьём какао по утрам. А еще всей толпой побили быбку-вахтёршу.
              Потому что у неё нет командного духа и вообще.
            </p>
            <p class="white">Анжела Топчий, коуч</p>
          </div>
          <div><img src="@/assets/angela.png" alt="Team Photo" /></div>
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
  name: "Frame5.3",
  components: {
    Hooper,
    Slide
  },
  data: () => ({
    options: {
      height: "max-content",
      itemsToShow: 1.3,
      centerMode: true
    }
  }),
  methods: {
    slidePrev() {
      this.$refs.carousel.slidePrev();
    },
    slideNext() {
      this.$refs.carousel.slideNext();
    }
  }
};
</script>

<style scoped lang="scss">
p {
  text-align: start;
}

.feedback {
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
      align-items: flex-start;
      justify-content: space-between;
      max-width: 400px;
      width: 90%;
      &:nth-child(1) {
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
        font-size: 14px;
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
        top: -10%;
      }
      img:not(.user) {
        max-width: 375px;
        margin: 20px auto;
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
    box-sizing: border-box;
    width: 100%;
    bottom: 0;
    padding: 0 3%;
  }

  @media (max-width: 1023px) {
    padding: 7% 20px 3%;
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
