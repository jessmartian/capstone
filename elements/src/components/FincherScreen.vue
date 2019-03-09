<template>
  <div class="fincher">
    <div class="fincher__topbar">
      Color / Lighting
    </div>
    <div class="fincher__container">
      <div class="fincher__description">
        <div class="fincher__description-title">Zodiac</div>
        <div class="fincher__description-body">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc a fermentum magna. Suspendisse vitae ligula vitae diam imperdiet finibus. Integer interdum, dolor non pellentesque elementum, nulla mi commodo mauris, id tincidunt lectus dolor sit amet turpis. Donec diam mi, aliquam id vestibulum id, posuere eu tortor.</div>
      </div>
      <div class="fincher__video">
        <div class="fincher__video-screen">
          Test
        </div>
        <div class="fincher__video-palette">
          <div v-for="color in palette" 
            :key="color"
            class="fincher__video-palette-color"
            :style="{ 'background-color': color }">
          </div>
        </div>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'FincherScreen',
  data() {
    return {
      palette: [
        '#291F0F',
        '#0E0800',
        '#D7D2C5',
        '#537C72',
        '#AA7D47',
      ]
    }
  }
};
</script>

<style scoped lang="scss">
.fincher {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  &__topbar {
    align-self: flex-start;
    margin: 2em;
    width: 100%;
    text-align: left;
    font-size: 2em;
  }
  &__container {
    display:flex; 
    justify-content: space-between;
    padding: 2em 10em;
    height: 40vh;
  }
  &__description {
    width: 50%;
    text-align: left;
    &-title {
      font-size: 36px;
      margin-bottom: 2em;
    }
    &-body {
      font-size: 16px;
      font-family: 'Open Sans', sans-serif;
      width: 60%;
      line-height: 2em;
    }
  }
  &__video {
    width: 50%;
    display: flex;
    flex-direction: column;
    &-screen {
      background-color: white;
      height: 80%;
      width: 100%;
    }
    &-palette {
      display: flex;
      height: 20%;
      width: 100%;
      background-color: black;
      &-color {
        width: 20%;
      }
    }
  }

}
</style>
