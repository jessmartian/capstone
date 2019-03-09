<template>
  <div class="intro">
    <div class="intro-box">
      <div class="intro__title">Elements</div>
      <div class="intro__description">
        A showcase of a director’s trademark style through elements of film.
      </div>
    </div>
    <div class="intro__credit">
      Curated by Jessica Martin
    </div>
  </div>
</template>

<script>
export default {
  name: 'Intro',
};
</script>

<style scoped lang="scss">
  .intro {
    &-box {
      display: flex;
      position: relative;
      border: 2px solid #FFFFFF;
      width: 775px;
      height: 400px;
    }
    &__title {
      font-family: 'Open Sans', sans-serif;
      position: absolute;
      left: -3em;
      top: 2em;
      font-size: 48px;
      font-weight: 700;
      text-transform: uppercase;
      letter-spacing: 1em;
    }
    &__description {
      position: absolute;
      right: 0;
      bottom: 0;
      margin: 2em;
      font-size: 16px;
      width: 20%;
      text-align: left;
    }
    &__credit {
      margin-top: 2em;
      font-size: 14px;
      text-transform: uppercase;
      letter-spacing: 0.5em;
    }
  }
</style>
