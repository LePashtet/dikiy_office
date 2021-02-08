<template>
  <section class="video">
    <div class="video-bg">
      <div class="video-bg">
        <iframe
          src="https://assets-iframe.ggwebcast.com/JLRGeneva2018/01/"
          loading="lazy"
          frameborder="0"
          allowtransparency="true"
          allow="encrypted-media"
        ></iframe>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Frame11"
};
</script>

<style scoped lang="scss">
.video {
  height: 100vh;
  box-sizing: border-box;
  position: relative;
  &__item {
    p {
      width: 50%;
    }
    & > .white {
      font-weight: 800;
      font-size: 64px;
      line-height: 78px;
      color: #ffffff;
      margin-bottom: 20px;
    }
    & > .small {
      font-weight: normal;
      font-size: 24px;
      line-height: 36px;
      color: #ffffff;
    }
  }

  .video-bg {
    background-size: cover;
  }
  .video-bg > iframe {
    position: absolute;
    top: 0;
    left: 0;
    min-width: 100%;
    min-height: 100%;
    width: auto;
    height: auto;
  }
  @supports (object-fit: cover) {
    .video-bg > iframe {
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
  }
}
</style>
