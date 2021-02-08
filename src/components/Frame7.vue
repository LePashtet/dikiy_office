<template>
  <section class="program">
    <h3>
      из чего <br />
      состоит <br />
      тренинг
    </h3>
    <p class="white">
      Этапы&nbsp;проведения тренинга
    </p>
    <div class="program__menu">
      <div
        class="program__menu-item"
        :class="{ active: active === i }"
        v-for="(item, i) in menu"
        :key="item.title"
        @click="setActive(i)"
      >
        <p v-html="item.title"></p>
        <img src="@/assets/plus.svg" alt="Plus" />
        <div class="text-wrp">
          <p class="text" v-html="item.text"></p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Frame7",
  data: () => ({
    menu: [
      {
        title: "1. Вводная лекция",
        text:
          "Тренинги проходят в игровом формате, в непринужденной и знакомой участникам обстановке. Фактически они напоминают игру, при том что хорошо прокачивают командную работу и коммуникацию. \n" +
          "\n" +
          "Участники сами не заметят, как приобретут важные для работы в команде навыки, сплотятся в дружный коллектив и примут на себя несвойственные им ранее задачи. И при этом будут считать этот тренинг отличным тимбилдингом! "
      },
      {
        title: "2. Три игровых тренинга",
        text:
          "Тренинги проходят в игровом формате, в непринужденной и знакомой участникам обстановке. Фактически они напоминают игру, при том что хорошо прокачивают командную работу и коммуникацию. \n" +
          "\n" +
          "Участники сами не заметят, как приобретут важные для работы в команде навыки, сплотятся в дружный коллектив и примут на себя несвойственные им ранее задачи. И при этом будут считать этот тренинг отличным тимбилдингом! "
      },
      {
        title: "3. Фидбек от коуча и психолога",
        text:
          "Тренинги проходят в игровом формате, в непринужденной и знакомой участникам обстановке. Фактически они напоминают игру, при том что хорошо прокачивают командную работу и коммуникацию. \n" +
          "\n" +
          "Участники сами не заметят, как приобретут важные для работы в команде навыки, сплотятся в дружный коллектив и примут на себя несвойственные им ранее задачи. И при этом будут считать этот тренинг отличным тимбилдингом! "
      }
    ],
    active: null
  }),
  methods: {
    setActive(num) {
      if (this.active === num) {
        this.active = null;
      } else {
        this.active = num;
      }
    }
  }
};
</script>

<style scoped lang="scss">
.program {
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
  p {
    text-align: start;
  }
  & > .white {
    font-weight: 800;
    font-size: 64px;
    line-height: 78px;
    color: #ffffff;
  }
  &__menu {
    width: 60%;
    min-height: 400px;
    height: 100%;
    &-item {
      display: grid;
      grid-template-areas:
        "p img"
        "text text";
      justify-content: space-between;
      padding-bottom: 10px;
      margin-top: 10px;
      border-bottom: 1px solid #ffffff;
      bottom: 0;
      p {
        font-weight: bold;
        font-size: 18px;
        line-height: 22px;
        color: #ff7e00;
      }
      p.text {
        font-weight: normal;
        font-size: 16px;
        line-height: 20px;
        color: #ffffff;
        margin: 10px 0 0 10px;
        width: 90%;
      }
      & > div {
        max-height: 0;
        transition: max-height 800ms ease-in-out;
        overflow: hidden;
      }
      &.active > div {
        max-height: 600px;
      }
      & > img {
        transform: rotateZ(0);
        transition-duration: 0.5s;
        justify-self: end;
      }
      &.active > img {
        transform: rotateZ(45deg);
        transition-duration: 0.5s;
      }
    }
  }
  @media (max-width: 1023px) {
    padding: 3% 20px 3%;
    height: 100vh;
    & > .white {
      font-weight: 800;
      font-size: 36px;
      line-height: 44px;
      color: #ffffff;
      max-width: 80%;
    }
    &__menu {
      width: 100%;
      &-item {
        grid-template-areas:
          "p img"
          ".text .text";
        & > p {
          font-weight: bold;
          font-size: 18px;
          line-height: 22px;
        }
        & > p.text {
          font-weight: normal;
          font-size: 16px;
          line-height: 20px;
          margin: 10px 0 0 10px;
        }
      }
    }
  }
}
</style>
