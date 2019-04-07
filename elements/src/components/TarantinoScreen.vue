<template>
  <div class="tarantino">
      <div class="topbar">Cinematography</div>
        <div class="container">
          <div class="tarantino-screen">
          </div>
          <div class="title">
            <div class="title-name">{{ title }}</div>
            <div class="title-shot"> Extreme Close-Up
            </div>
          </div>
          <input type="range" min="1" max="100" class="slider" v-model="shotSlider">
          <div class="description">
            <div class="description-body">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc a fermentum magna. Suspendisse vitae ligula vitae diam imperdiet finibus. Integer interdum, dolor non pellentesque elementum, nulla mi commodo mauris, id tincidunt lectus dolor sit amet turpis. Donec diam mi, aliquam id v estibulum id, posuere eu tortor.</div>
          </div>
        </div>
    </div>
</template>

<script>
  export default {
    name: 'TarantinoScreen',
    data() {
      return {
        shotSlider: 0,
        title: null,
        items: [
          {
            movieName: 'movieName',
            cameraShot: 'cameraShot',
            description: 'description',
            video: 'video source'
          }
        ]
      }
    },
    watch: {
      shotSlider() {
        if (this.shotSlider >= 0 && this.shotSlider <= 16) {
          this.title = 'First Video'
        } else if (this.shotSlider > 16 && this.shotSlider < 32) {
          this.title = 'Second Video'
        } else if (this.shotSlider > 32 && this.shotSlider < 48) {
          this.title = 'Third Video'
        } else if (this.shotSlider > 48 && this.shotSlider < 64) {
          this.title = 'Fourth Video'
        } else if (this.shotSlider > 64 && this.shotSlider < 80) {
          this.title = 'Fifth Video'
        } else if (this.shotSlider > 80 && this.shotSlider <= 100) {
          this.title = 'Sixth Video'
        }
      }
    },
    methods: {
    }
  }
</script>

<style scoped lang="scss">
  .tarantino {
    background-color: #2B2B31;
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .topbar {
    align-self: flex-start;
    width: 100%;
    text-align: left;
    font-size: 2em;
    text-align: left;
    font-size: 2em;
    color: white;
    padding: 2em 0 0 2em;  
  } 
  .container {
    background-color: #2B2B31;
    justify-content: space-between; 
    width: 100%;
    height: 100%;
  }
  .tarantino-screen {
    background-color: #FFFFFF;
    display: flex;
    width: 725px;
    height: 300px;
    margin: 5% auto;
    margin-top: 75px;
    box-shadow: 7px 0px 20px rgba(255, 255, 255, 0.25);
  }
  .title {
    display: flex;
    margin: 2em auto;
    width: 725px;
  }
  .title-name {
    font-size: 25px;
    color: #ffffff;
		text-align: right;
    position: absolute;
  }
  .title-shot {
    line-height: 1;
		font-weight: bold;
    font-size: 32px;
    color: #ffffff;
    padding-left: 65%;
  }
  .description {
    align-self: flex-end;
    width: 100%;
    display: flex;
    justify-content: center;
  }
  .description-body {
    width: 50%;
    display: flex;
    margin: auto;
    padding: 1em;
    font-size: 18px;
    color: white;
    text-align:center;
  }
  .slider {
    width: 70%;
    -webkit-appearance: none;
    height: 10px;
    border-radius: 2em;
    background: white;
    outline: none;
  }
  .slider::-moz-range-thumb {
    width: 25px;
    height: 25px;
    background: #4CAF50;
    cursor: pointer;
  }
  .slider::-webkit-slider-thumb {
    -webkit-appearance: none;
    appearance: none;
    width: 25px;
    height: 25px;
    border-radius: 2em;
    background: #F9812A;
    cursor: pointer;
  }
</style>