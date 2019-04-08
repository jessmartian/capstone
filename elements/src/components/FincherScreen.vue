<template>
  <div class="fincher">
    <div class="fincher__topbar">
      Color / Lighting
    </div>
    <div class="fincher__container">
      <div class="fincher__description">
        <div class="fincher__description-title">{{ selectedPallete.movieName }}</div>
        <div class="fincher__description-body">{{ selectedPallete.description}}</div>
      </div>
      <div class="fincher__selected">
        <div class="fincher__selected-screen">
          <video controls :src="selectedPallete.video"></video>
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
  data() {
    return {
      selectedPallete: {
        key: 0,
        description: 'Fincher uses monochromatic colours to convey the ridged worldviews of unbalanced characters',
        movieName: 'Fight Club',
        colors: [
          '#677645',
          '#D2DDAB',
          '#8C8B7E',
          '#A3A176',
          '#58543A',
        ],
      },
      palettes: [
        {
          key: 1,
          description: 'Discordant colours of the prison jumpsuits are used to draw the attention to out-of-place elements to build anticipation and portray the importance of the items',
          movieName: 'Se7en',
          video: '',
          colors: [
            '#70714C',
            '#A4A06F',
            '#950000',
            '#EA0000',
            '#280000',
          ],
        },
        {
          key: 2,
          description: 'The contrasting colours of blue and yellow represent conflict both inside and out. The night sky, city buildings and the characters clothes represent a dark, midnight blue, a calm and mysterious representation of what is to come. The yellow of the explosions represent the breaking of stability, of not only the buildings outside but possibility of the characters too. ',
          movieName: 'Fight Club',
          video: '',
          colors: [
            '#0D313F',
            '#004E5E',
            '#8A5D28',
            '#A9805A',
            '#0C0B0E',
          ],
        },
        {
          key: 3,
          description: 'We see Fincher use the discord of blue and yellow to represent the contrast and argument between two characters in this scene, this is ultimately two opposing sides of the characters and the set',
          movieName: 'The Social Network',
          video: '../src/assets/TSNTwo.mp4',
          colors: [
            '#2B365D',
            '#B9B906',
            '#A49E74',
            '#C18D00',
            '#5D2F01',
          ],
        },
        {
          key: 4,
          description: 'Discordant colours such as the blue and brown nature landscape is used to draw the attention to out-of-place elements such as the black hooded man to build anticipation and portray the importance of the items',
          movieName: 'Zodiac',
          video: '',
          colors: [
            '#291F0F',
            '#0E0800',
            '#D7D2C5',
            '#537C72',
            '#AA7D47',
          ],
        },
      ],
      video: {
        sources: [{
                  src: '',
                  type: 'video/.mp4'
        }],
        options: {
                  autoplay: true,
                  volume: 0.6,
                }
      }
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
