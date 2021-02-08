<template>
  <section class="free">
    <p class="white">Бесплатно проводим первый тренинг- <br />презентацию</p>
    <p class="small">
      Просто оставьте номер телефона — мы свяжемся с вами сегодня же и расскажем
      подробности.
    </p>
    <my-button @click="scroll" text="Оставить заявку"></my-button>
  </section>
</template>

<script>
import myButton from "@/components/button";
export default {
  name: "Frame4",
  components: {
    myButton
  },
  methods: {
    scroll() {
      this.$scrollTo("#my-footer", 3000);
    }
  }
};
</script>

<style scoped lang="scss">
.free {
  height: 100%;
  min-height: 100vh;
  box-sizing: border-box;
  padding: 3% 200px 3%;
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: space-around;
  text-align: start;

  p {
    width: 60%;
  }
  & > .white {
    font-weight: 800;
    font-size: 64px;
    line-height: 78px;
    color: #ffffff;
  }
  & > .small {
    font-weight: normal;
    font-size: 24px;
    line-height: 36px;
    color: #ffffff;
    margin: 20px 0;
  }
  @media (max-width: 1023px) {
    height: 100vh;
    padding: 3% 20px 3%;
    p {
      width: 90%;
    }
    & > .white {
      font-weight: 800;
      font-size: 36px;
      line-height: 44px;
      color: #ffffff;
    }
    & > .small {
      font-weight: normal;
      font-size: 18px;
      line-height: 25px;
      color: #ffffff;
    }
  }
}
</style>
