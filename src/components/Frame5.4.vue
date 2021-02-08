<template>
  <section class="how">
    <h3>
      как <br />
      проходит <br />тренинг
    </h3>
    <article class="how__item">
      <img src="@/assets/offline.png" alt="Offline Meeting" />
      <p class="white">Офлайн</p>
      <p class="small">
        Мы проводим все тренинги комплекса в удобной вам локации — у вас в офисе
        или на нашей территории.
        <br />
        <br />
        Непринужденная атмосфера даст максимальную вовлеченность в процесс.
        <br />
        <br />
        Идеальное сочетание игрового мероприятия и командного тренинга.
      </p>
    </article>
    <article class="how__item">
      <img src="@/assets/online.png" alt="Online Meeting" />
      <p class="white">Онлайн</p>
      <p class="small">
        Технологии, которые мы используем, помогают видеть реакции каждого
        участника тренинга.
        <br />
        <br />
        Требования к каждому сотруднику — лишь наличие стабильного
        интернет-соединения.
        <br />
        <br />
        Идеально для команд, работающих удалённо.
      </p>
    </article>
  </section>
</template>

<script>
export default {
  name: "Frame5.4"
};
</script>

<style scoped lang="scss">
.how {
  height: 100%;
  min-height: 150vh;
  box-sizing: border-box;
  padding: 3% 200px 3%;
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: space-around;
  text-align: start;
  background: #343434;

  &__item {
    display: grid;
    grid-template-areas: "imag head" "imag txt";
    grid-column-gap: 10%;

    & > .white {
      font-weight: 800;
      font-size: 64px;
      line-height: 78px;
      color: #ffffff;
      margin-bottom: 20px;
      grid-area: head;
    }
    & > .small {
      font-weight: normal;
      font-size: 18px;
      line-height: 24px;
      letter-spacing: 0.05em;
      color: #ffffff;
      grid-area: txt;
    }
    & > img {
      grid-area: imag;
    }
  }

  @media (max-width: 1023px) {
    height: 150vh;
    padding: 3% 20px 3%;
    &__item {
      grid-template-areas: "head" "txt" "imag";
      grid-column-gap: 10%;
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
        font-size: 14px;
        line-height: 18px;
        color: #ffffff;
      }
      img {
        max-width: 100%;
        margin-top: 50px;
      }
    }
  }
}
</style>
