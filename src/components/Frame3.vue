<template>
  <section class="numbers">
    <img src="@/assets/women.webp" alt="Women" />
    <div class="numbers-item" v-for="item in list" :key="item.text">
      <span class="orange" v-html="item.num"></span>
      <p class="white" v-html="item.text" :style="item.style"></p>
    </div>
  </section>
</template>

<script>
export default {
  name: "Frame3",
  data: () => ({
    list: [
      {
        num: "37",
        text: "проведенных <br>тренингов",
        style: "bottom: -1%"
      },
      {
        num: "680",
        text: `человек <br> прошло <br> нашу игру`,
        style: "bottom: -7%"
      },
      {
        num: "12",
        text: "компаний <br> заказали игру <br> повторно",
        style: "bottom: -9%"
      }
    ]
  })
};
</script>

<style scoped lang="scss">
.numbers {
  background: #343434;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: space-around;
  box-sizing: border-box;
  padding: 3% 200px 3%;
  position: relative;
  height: 100%;
  min-height: 100vh;
  &-item {
    position: relative;
    text-align: start;
    z-index: 2;
    p {
    }
    & > .orange {
      font-weight: 800;
      font-size: 210px;
      line-height: 256px;
      -webkit-text-stroke: 2px #ff7e00;
      text-stroke: 2px #ff7e00;
      box-sizing: border-box;
      color: rgba(#343434, 0);
    }
    & > .white {
      font-weight: 600;
      font-size: 24px;
      line-height: 34px;
      color: #ffffff;
      position: absolute;
      width: max-content;
      bottom: -5%;
      left: 2%;
    }
  }
  img {
    position: absolute;
    top: 0;
    left: 30%;
    z-index: 0;
    width: 50%;
  }
  @media (max-width: 1023px) {
    padding: 0;
    height: 150vh;
    &-item {
      margin: 0 20px 0;
      & > .orange {
        font-size: 140px;
        line-height: 171px;
      }
    }
    img {
      position: relative;
      left: 0;
      width: 100%;
      height: auto;
    }
  }
}
</style>
