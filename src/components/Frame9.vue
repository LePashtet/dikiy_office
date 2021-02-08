<template>
  <section class="first">
    <h3>
      как <br />
      заказать <br />тренинг
    </h3>
    <article class="first__item">
      <p class="white">Оставьте заявку на&nbsp;сайте</p>
      <p class="small">
        Прямо сейчас вы можете заполнить простую форму, и мы свяжемся с вами в
        удобное время. Обсудим условия проведения тренинга, ответим на все ваши
        вопросы и выясним ключевые потребности и ожидания от игры.
      </p>
    </article>
    <article class="first__item">
      <p class="white">
        Первый&nbsp;презентационный тренинг&nbsp;мы&nbsp;проведём бесплатно
      </p>
      <p class="small">
        Мы покажем, насколько полезна и увлекательна игра "Дикий офис" и
        коллектив уже с первой пробы почувствует влияние тренинга.
      </p>
    </article>

    <my-button @click="scroll" text="Оставить заявку"></my-button>
    <div class="color-bg"></div>
    <div class="video-bg">
      <div class="video-bg">
        <video width="100%" muted height="100vh" loop preload autoplay>
          <source src="@/assets/v2.mp4" type="video/mp4" />
        </video>
      </div>
    </div>
  </section>
</template>

<script>
import myButton from "@/components/button";
export default {
  name: "Frame9",
  components: {
    myButton
  },
  methods: {
    scroll() {
      this.$scrollTo("#my-footer", 1000);
    }
  }
};
</script>

<style scoped lang="scss">
.first {
  height: 100%;
  min-height: 140vh;
  box-sizing: border-box;
  padding: 3% 200px 3%;
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: space-around;
  text-align: start;

  &__item {
    p {
      width: 80%;
    }
    & > .white {
      font-weight: 800;
      font-size: 64px;
      line-height: 70px;
      color: #ffffff;
      margin-bottom: 40px;
    }
    & > .small {
      font-weight: normal;
      font-size: 24px;
      line-height: 36px;
      color: #ffffff;
      margin-bottom: 80px;
    }
  }

  .video-bg {
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    overflow: hidden;
    z-index: -2;
    background-size: cover;
  }
  .video-bg > video {
    position: absolute;
    top: 0;
    left: 0;
    min-width: 100%;
    min-height: 100%;
    width: auto;
    height: auto;
  }
  @supports (object-fit: cover) {
    .video-bg > video {
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
  }
  .color-bg {
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    overflow: hidden;
    z-index: -1;
    background-size: cover;
    background: linear-gradient(
      90deg,
      rgba(52, 52, 52, 0.31) 0%,
      #423b3b 80.97%
    );
    mix-blend-mode: multiply;
  }
  @media (max-width: 1023px) {
    height: 150vh;
    padding: 3% 20px 3%;
    &__item {
      p {
        width: 100%;
      }
      & > .white {
        font-weight: 800;
        font-size: 34px;
        line-height: 44px;
        color: #ffffff;
        margin-bottom: 20px;
      }
      & > .small {
        font-weight: normal;
        font-size: 18px;
        line-height: 25px;
        color: #ffffff;
      }
    }
  }
}
</style>
