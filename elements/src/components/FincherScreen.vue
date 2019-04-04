<template>
  <div class="fincher">
    <div class="fincher__topbar">
      Color / Lighting
    </div>
    <div class="fincher__container">
      <div class="fincher__description">
        <div class="fincher__description-title">Zodiac</div>
        <div class="fincher__description-body">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc a fermentum magna. Suspendisse vitae ligula vitae diam imperdiet finibus. Integer interdum, dolor non pellentesque elementum, nulla mi commodo mauris, id tincidunt lectus dolor sit amet turpis. Donec diam mi, aliquam id v estibulum id, posuere eu tortor.</div>
      </div>
      <div class="fincher__selected">
        <div class="fincher__selected-screen">
          <video controls
            class="fincher__selected-screen--video">
          </video>
        </div>
        <div class="fincher__selected-palette">
          <div v-for="color in selectedPallete.colors"
            :key="color"
            class="fincher__selected-palette-color"
            :style="{ 'background-color': color }">
          </div>
        </div>
      </div>
    </div>
    <div class="fincher__palettes">
      <div class="fincher__palettes-palette"
        v-for="palette in palettes"
        :key="palette.video"
        @click="selectPalette(palette)">
        <div class="fincher__palettes-palette-color"
          v-for="color in palette.colors"
          :key="color"
          :style="{ 'background-color': color }">
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'FincherScreen',
  computed: {
    video() {
      return this.selectedPallete.video;
    },
  },
  data() {
    return {
      selectedPallete: {
        colors: [
          '#677645',
          '#D2DDAB',
          '#8C8B7E',
          '#A3A176',
          '#58543A',
        ],
      },
      //TO DO: change all the colours plz//
      palettes: [
        {
          colors: [
            '#70714C',
            '#A4A06F',
            '#950000',
            '#EA0000',
            '#280000',
          ],
        },
        {
          video: 'source of video here1',
          colors: [
            '#0D313F',
            '#004E5E',
            '#8A5D28',
            '#A9805A',
            '#0C0B0E',
          ],
        },
        {
          video: 'source of video here1',
          colors: [
            '#2B365D',
            '#B9B906',
            '#A49E74',
            '#C18D00',
            '#5D2F01',
          ],
        },
        {
          video: 'source of video here1',
          colors: [
            '#677645',
            '#D2DDAB',
            '#8C8B7E',
            '#A3A176',
            '#58543A',
          ],
        },
      ],
    };
  },
  methods: {
    selectPalette(palette) {
      this.selectedPallete = palette;
      console.log(palette);
    },
  },
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
      width: 90%;
      line-height: 2em;
    }
  }
  &__selected {
    width: 640px;
    display: flex;
    flex-direction: column;
    &-screen {
      background-color: white;
      height: 95%;
      width: 100%;
      &--video {
        width:100%;
        height:100%;
      }
    }
    &-palette {
      display: flex;
      height: 5%;
      width: 100%;
      background-color: black;
      &-color {
        width: 20%;
        }
      }
    }
  &__palettes {
    display: flex;
    justify-content: space-around;
    align-items: center;
    margin: 4em auto;
    width: 80%;
    height: 10%;
    &-palette {
      display: flex;
      height: 50%;
      width: 25%;
      background-color: white;
      padding: 1%;
      cursor: pointer;
      &-color {
        width: 20%;
        }
      }
  }
}
</style>
