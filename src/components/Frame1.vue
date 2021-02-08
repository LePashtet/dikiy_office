<template>
  <section class="main">
    <div class="main__top">
      <img src="@/assets/logo.svg" alt="Logo" />
      <my-button @click="scroll" text="Оставить заявку"></my-button>
    </div>
    <div class="main__bottom">
      <h3>
        игровой<br />комплекc<br />тренингов
        <span style="font-size: 40px; line-height: 0;">*</span>
      </h3>
      <h1>«Дикий <br />&nbsp; офис» —</h1>
      <h2>&nbsp; Драйв, эволюция, результат!</h2>
      <img
        @click="$scrollTo('#frame2', 500)"
        src="@/assets/arrow.svg"
        alt="Arrow down"
      />
    </div>
    <div class="color-bg"></div>
    <div class="video-bg">
      <div class="video-bg">
        <video width="100%" muted height="100vh" loop preload autoplay>
          <source src="@/assets/v1.mp4" type="video/mp4" />
        </video>
      </div>
    </div>
    <img
      src="@/assets/free.svg"
      alt=""
      @click="$scrollTo('#frame9', 1000)"
      id="free"
    />
  </section>
</template>

<script>
import myButton from "@/components/button";
export default {
  name: "Frame1",
  components: {
    myButton
  },
  methods: {
    scroll() {
      this.$scrollTo("#my-footer", 5000);
    }
  }
};
</script>

<style scoped lang="scss">
.main {
  height: 100%;
  min-height: 100vh;
  box-sizing: border-box;
  padding: 3% 200px 0;
  position: relative;

  &__top {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  &__bottom {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    max-width: 70%;
    margin-top: 15%;
    h2 {
      font-weight: normal;
      font-size: 32px;
      line-height: 39px;
      color: #ffffff;
      position: absolute;
      bottom: 10%;
    }
    h1 {
      font-weight: 900;
      font-size: 102px;
      letter-spacing: 0.05em;
      text-transform: uppercase;
      text-align: start;
      color: #ffffff;
      margin: 10% 0;
      white-space: pre;
      pre {
        font-weight: 900;
        font-size: 102px;
        text-transform: uppercase;
        text-align: start;
        color: #ffffff;
      }
    }
    img {
      width: 50px;
      height: 50px;
      position: absolute;
      bottom: 3%;
      -webkit-animation: 1s ease-in-out 0s infinite normal move;
      -moz-animation: 1s ease-in-out 0s infinite normal move;
      -o-animation: 1s ease-in-out 0s infinite normal move;
      animation: 1s ease-in-out 0s infinite normal move;
    }
  }
  .video-bg {
    position: fixed;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    overflow: hidden;
    z-index: -3;
    background-size: cover;
  }
  .video-bg > video {
    position: relative;
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
    position: fixed;
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
  #free {
    position: absolute;
    bottom: 5%;
    right: 5%;
  }
  @media (max-width: 1023px) {
    padding: 3% 20px 0;
    &__top {
      img {
        width: 100px;
      }
    }

    &__bottom {
      display: flex;
      flex-direction: column;
      align-items: flex-start;
      max-width: 100%;
      margin-top: 15vh;
      h2 {
        font-weight: normal;
        font-size: 18px;
        line-height: 24px;
        color: #ffffff;
        position: relative;
        bottom: 10%;
        max-width: 70%;
        text-align: start;
      }
      h1 {
        font-weight: 900;
        font-size: 51px;
        letter-spacing: 0.05em;
        text-transform: uppercase;
        text-align: start;
        color: #ffffff;
        margin: 10% 0;
      }
      img {
        width: 50px;
        height: 50px;
        position: absolute;
        bottom: 3%;
      }
    }
  }
}
@-webkit-keyframes move {
  0% {
    bottom: 3%;
  }
  50% {
    bottom: 1.5%;
  }
  100% {
    bottom: 3%;
  }
}
@-moz-keyframes move {
  0% {
    bottom: 3%;
  }
  50% {
    bottom: 1.5%;
  }
  100% {
    bottom: 3%;
  }
}
@-o-keyframes move {
  0% {
    bottom: 3%;
  }
  50% {
    bottom: 1.5%;
  }
  100% {
    bottom: 3%;
  }
}
@keyframes move {
  0% {
    bottom: 3%;
  }
  50% {
    bottom: 1.5%;
  }
  100% {
    bottom: 3%;
  }
}
</style>
