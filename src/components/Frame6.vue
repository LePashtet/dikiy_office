<template>
  <section class="about">
    <h3>
      что такое <br />
      «дикий <br />
      офис»
    </h3>
    <p class="orange">
      «Дикий <br class="mobile" />офис» — <br />комплексный&nbsp;уникальный
      ролевой&nbsp;корпоративный тренинг&nbsp;с&nbsp;детективным сюжетом
    </p>
    <p class="gray">
      Суть игры — в компанию под видом обычных офисных работников внедряются
      рейдеры. Их задача — уволить директора и захватить власть.
      <br /><br />
      Цель каждого участника — привести команду к победе в борьбе за выживание.
    </p>
    <div class="color-bg"></div>
    <div class="video-bg">
      <video width="100%" height="100vh" muted preload autoplay loop>
        <source src="@/assets/v4.mp4" type="video/mp4" />
      </video>
    </div>
  </section>
</template>

<script>
export default {
  name: "Frame6",
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
.about {
  height: 100%;
  min-height: 100vh;
  box-sizing: border-box;
  padding: 3% 200px 3%;
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: space-around;
  p {
    text-align: start;
  }
  & > .orange {
    font-weight: 800;
    font-size: 60px;
    letter-spacing: 0.01em;
    color: #ff7e00;
  }
  & > .gray {
    font-weight: normal;
    font-size: 18px;
    line-height: 24px;
    letter-spacing: 0.05em;
    color: #ffffff;
    width: 50%;
  }
  .mobile {
    display: none;
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
    padding: 3% 20px 3%;

    .mobile {
      display: block;
    }
    & > .orange {
      font-weight: 800;
      font-size: 36px;
      line-height: 109.6%;
      letter-spacing: 0.01em;
      color: #ff7e00;
    }
    & > .gray {
      font-weight: normal;
      font-size: 16px;
      line-height: 20px;
      letter-spacing: 0.05em;
      color: #ffffff;
      width: 70%;
    }
  }
}
</style>
