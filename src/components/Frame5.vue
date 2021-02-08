<template>
  <section class="mission">
    <h3>
      в чём <br />
      наша <br />
      миссия
    </h3>
    <p class="orange">
      Мы делаем вашу&nbsp;команду единым&nbsp;организмом, способным&nbsp;решить
      любые&nbsp;задачи.
    </p>
  </section>
</template>

<script>
export default {
  name: "Frame5"
};
</script>

<style scoped lang="scss">
p {
  text-align: start;
}

.mission {
  height: 100%;
  min-height: 100vh;
  box-sizing: border-box;
  padding: 3% 200px 3%;
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: space-around;
  background: #343434;

  & > .orange {
    font-weight: 800;
    font-size: 74px;
    letter-spacing: 0.01em;
    color: #ff7e00;
  }
  .mobile {
    display: none;
  }

  @media (max-width: 1023px) {
    padding: 3% 20px 3%;
    min-height: 70vh;

    .mobile {
      display: block;
    }
    & > .orange {
      font-weight: 800;
      font-size: 36px;
      line-height: 109.6%;
      letter-spacing: 0.01em;
      color: #ff7e00;
      max-width: 20px;
    }
  }
}
</style>
