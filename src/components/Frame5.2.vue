<template>
  <section class="success">
    <img src="@/assets/people1.webp" alt="People" />

    <h3>
      что мы<br />
      дадим <br />
      вам
    </h3>
    <p class="white">Мы приносим успех. <br />Почему?</p>
    <div class="success__tips">
      <div class="tip">
        <img src="@/assets/tip1.svg" alt="Icon" />
        <p>Раскрываем скрытый потенциал каждого</p>
      </div>
      <div class="tip">
        <img src="@/assets/tip2.svg" alt="Icon" />
        <p>Развиваем ментальные способности</p>
      </div>
      <div class="tip">
        <img src="@/assets/tip3.svg" alt="Icon" />
        <p>Развиваем навыки командной работы</p>
      </div>
      <div class="tip">
        <img src="@/assets/tip4.svg" alt="Icon" />
        <p>Эффективность команды возрастает в разы</p>
      </div>
    </div>
    <my-button
      text="Оставить заявку"
      @click="$scrollTo('#my-footer', 2000)"
    ></my-button>
  </section>
</template>

<script>
import myButton from "@/components/button";
export default {
  name: "Frame5.2",
  components: {
    myButton
  },
  data: () => ({
    list: [
      {
        title: "Хотите настроить команду на продуктивную работу?",
        text:
          "Мы поможем прокачать коллектив на полную, добиться максимума от каждого члена команды и сплотить сотрудников вокруг общей миссии.  А заодно повысить их лояльность."
      },
      {
        title: "Хотите развить внимание, концентрацию и мышление?",
        text:
          "Мы поможем вам стать эффективнее, развить коммуникативные навыки, вливаться в любую команду, отставивать свою позицию и идеи."
      },
      {
        title: "Хотите повысить качество коммуникации в команде? ",
        text:
          "Мы поможем научить сотрудников организовывать ситуативные команды под самые разные типы задач, улучшим взаимопонимание между ними и психологический климат в компании. "
      }
    ]
  })
};
</script>

<style scoped lang="scss">
p {
  text-align: start;
}

.success {
  height: 100%;
  min-height: 100vh;
  box-sizing: border-box;
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: space-around;
  background: #343434;
  &:nth-child(n):not(img) {
    padding: 3% 200px 3%;
  }

  & > img {
    position: absolute;
    top: -5%;
    right: 5%;
    z-index: 0;
    max-width: 100%;
    width: 50%;
  }
  .white {
    font-weight: 800;
    font-size: 64px;
    line-height: 78px;
    color: #ffffff;
    position: relative;
    z-index: 10;
  }
  &__tips {
    display: flex;
    justify-content: space-between;
    width: 100%;

    .tip {
      font-weight: normal;
      font-size: 18px;
      line-height: 22px;
      letter-spacing: 0.05em;
      color: #ffffff;
      display: flex;
      flex-direction: column;
      align-items: flex-start;

      img {
        margin-bottom: 20px;
      }
      p {
        max-width: 150px;
      }
    }
  }

  @media (max-width: 1023px) {
    min-height: 150vh;

    &:nth-child(n):not(img) {
      padding: 3% 20px 3%;
    }

    & > img {
      position: relative;
      top: 0;
      right: 0;
      margin-bottom: 50px;
      width: 100%;
    }
    .white {
      font-size: 36px;
      line-height: 44px;
    }
    &__tips {
      display: flex;
      flex-direction: column;
      justify-content: flex-start;
      align-items: flex-start;
      width: 50%;

      .tip {
        margin-bottom: 30px;

        img {
          margin-bottom: 20px;
        }
        p {
          max-width: 150px;
        }
      }
    }
  }
}
</style>
