<template>
  <div class="tarantino">
      <div class="topbar">Cinematography</div>
        <div class="container">
          <div class="tarantino-screen">
          </div>
          <div class="title">
            <div class="title-name">{{ current.movieName }}</div>
            <div class="title-shot">{{ current.cameraShot }}</div>
          </div>
          <input type="range" min="1" max="100" class="slider" v-model="shotSlider">
          <div class="description">
            <div class="description-body">{{ current.description }}</div>
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
        currentIndex: 0,
        items: [
          {
            movieName: 'Kill Bill: Vol. 1 (2003)',
            cameraShot: 'Extreme Close up',
            description: 'Tarantino dives in close to show an audience detail on what is important. With his unnerving foot fetish, this “big toe” scene creates a style of tension and suspense that leads up to the extreme close-up shot These close shots are meant to reveal more about a character then an audience could just grasp from dialogue.',
            video: 'video source'
          },
          {
            movieName: 'Django Unchained (2012)',
            cameraShot: 'Crash Zooms',
            description: 'A “Crash Zoom” also known as a snap zoom, is a sudden, rapid zoom in on an object or person. As you see in Django Unchained, the intense effect heightens the drama around any moment. ',
            video: 'video source'
          },
          {
            movieName: 'Trunk Compilation',
            cameraShot: 'Low Angle',
            description: 'The absolute trademark of Tarantino is his trunk shot camera angle, his use of it in every movie is for the audience to feel as if they are right there with the characters. The claustrophobic feeling of the “trunk technique” ensures the audience will be. He also uses reverse trunk shots with characters being watched from outside the trunk.',
            video: 'video source'
          },
          {
            movieName: 'Reservoir Dogs (1992)',
            cameraShot: 'Staged Wide Shot',
            description: 'This shot is mainly used when a director wants the audience to appreciate the full scope of a subject’s predicament within those surroundings. In the case of the Mexican Standoff, the audience can see that each character has full range of shooting each other within an empty space. The audience is directed to the actions of the characters rather than the environment.  ',
            video: 'video source'
          },
          {
            movieName: 'Jackie Brown (1997)',
            cameraShot: 'Tracking Long Shot',
            description: 'Tarantino uses these shots to stay with the same character or characters for several minutes as they perform actions or interact with each other. The opening sequence follows the character of Jackie, as she makes her way towards her workplace, only rushing towards the end when she realizes she is late. ',
            video: 'video source'
          },
          {
            movieName: 'The Hateful Eight (2015)',
            cameraShot: 'Establishing Location Shot',
            description: 'As Tarantino likes to keep things up-close and personal, he still has a stylistic eye when showing a location establishing shot. The establishing shots provide the audience where and when the next scene will occur. In Tarantino’s case, he frequently uses these shots when characters are telling a story or a flashback is taking place. ',
            video: 'video source'
          },
        ]
      }
    },
    computed: {
      current() {
        return this.items[this.currentIndex]
      }
    },
    watch: {
      shotSlider() {
        if (this.shotSlider >= 0 && this.shotSlider <= 16) {
          this.currentIndex = 0
        } else if (this.shotSlider > 16 && this.shotSlider < 32) {
          this.currentIndex = 1
        } else if (this.shotSlider > 32 && this.shotSlider < 48) {
          this.currentIndex = 2
        } else if (this.shotSlider > 48 && this.shotSlider < 64) {
          this.currentIndex = 3
        } else if (this.shotSlider > 64 && this.shotSlider < 80) {
          this.currentIndex = 4
        } else if (this.shotSlider > 80 && this.shotSlider <= 100) {
          this.currentIndex = 5
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
    font-size: 28px;
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
    padding: 2em;
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