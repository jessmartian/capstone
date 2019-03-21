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
      <div class="fincher__selected">
        <div class="fincher__selected-screen">
          <video controls
            class="fincher__selected-screen--video">
            <source :src="video" type="video/mp4">
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
      return this.selectedPallete.video
    }
  },
  data() {
    return {
      selectedPallete: {
        video: '../assets/videos/Fincher/FightClub-Endingscene.mp4',
        colors: [
          '#291F0F',
          '#0E0800',
          '#D7D2C5',
          '#537C72',
          '#AA7D47',
        ]
      },
      //TO DO: change all the colours plz
      palettes: [
        {
          video: '../assets/videos/Fincher/FightClubInsomniascene.mp4',
          colors: [
            '#291F0F',
            '#0k0800',
            '#D7l2C5',
            '#538C72',
            '#AA7D47',
          ]
        },
        {
          video: 'source of video here1',
          colors: [
            '#292F0F',
            '#0E0900',
            '#D7F2C5',
            '#537D72',
            '#AA7E47',
          ]
        },
      ]
     }
  },
  methods: {
    selectPalette(palette) {
      this.selectedPallete = palette
      console.log(palette)
    }
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
      width: 60%;
      line-height: 2em;
    }
  }
  &__selected {
    width: 655px;
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
    background:#FFFFFF;
    width: 80%;
    height: 15%;
    &-palette {
      display: flex;
      height: 50%;
      width: 25%;
      background-color: black;
      cursor: pointer;
      &-color {
        width: 20%;
        }
      }
  }
}
</style>
