<template>
  <div class="wright">
    <div class="topbar"> Sound Effects </div>
      <div class="container">
          <div class="player">
            <div class="player-title">
              <div class="songs">
                <div class="songs-title">{{ current.songTitle }}</div>
                <div class="songs-movie">{{ current.movieName }}</div>
              </div>
            </div>
            <div class="player-controls">
              <div class="player-image"></div>
              <div class="player-buttons">
                <button @click="previous" class="player-button">
                  <i class="material-icons">fast_rewind</i>
                </button>
                <template v-if="isPlaying">
                  <button @click="playToggle" class="player-button">
                    <i class="material-icons" style="font-size:90px">pause</i>
                  </button>
                </template>
                <template v-else>
                  <button @click="playToggle" class="player-button">
                    <i class="material-icons" style="font-size:90px">play_arrow</i>
                  </button>
                </template>
                <button @click="next" class="player-button">
                  <i class="material-icons">fast_forward</i>
                </button>
              </div>
            </div>
          </div>
    </div>
    <div class="description">
      <div class="description-body">{{ current.description }}</div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'WrightScreen',
    computed: {
      current() {
        return this.songs[this.currentIndex]
      },
    },
    data() {
      return {
        isPlaying: false,
        currentIndex: 0,
        songs: [
          {
            songTitle: 'Alabama Song',
            movieName: 'The World\'s End',
            videoSource: '../src/assets/Wright/TWEOne.mp4',
            description: 'Editing music to the beat of action (in this case, characters walking and suspiciously taking in their surroundings). This is effective for progressing the storyline further by condensing time as well as incorporating comedic relief in an otherwise tense scene.'
          },
          {
            songTitle: 'The Twins',
            movieName: 'Scott Pilgram VS the World',
            videoSource: '../src/assets/Wright/SPOne.mp4',
            description: 'A great example of how he incorporates the use of sound effects from video games, (ie. Collecting coins or points in a game) within a film. The scene is ultimately a battle of sound and music. '
          },
          {
            songTitle: 'Sound Effect Compilation',
            movieName: 'Varity',
            videoSource: '../src/assets/Wright/SEffectComp.mp4',
            description: 'This is a compilation of jump-cuts and sound effects from a range of Edgar Wright films. The jump-cuts are an editing technique that jumps in time or shows a person or object from different angles. Certain cuts are used to progress the plot, while others also emphasize important objects. These jump cuts are edited to amplify certain sound effects (usually of mundane or ordinary actions, like pouring a drink), which can underscore the importance of that object for a character or plot, create symbolism or metaphor, and most importantly create a comedic effect in an otherwise routine scene.  '
          },
          {
            songTitle: 'Oblivious to the Zombies',
            movieName: 'Shaun of the Dead',
            videoSource: '../src/assets/Wright/SotDOne.mp4',
            description: 'When returning from an identical trip to the store that was shown earlier in the film, the television voices are clipped together to provide information to the audience of what cause the apocalyptic environment but could be otherwise oblivious to the character. This scene also provides an example of how there is never silence within Wrights films, there is always amplified sound to intrigue the viewer '
          },
          {
            songTitle: 'Opening Sequence',
            movieName: 'Baby Driver',
            videoSource: '../src/assets/Wright/BBDriver.mp4',
            description: 'Getting the actors to sing or dance to the music creates an emotional connection to the audience. The audience may want to sing along but also are attentive to the characters of how much they enjoy it as well. We begin to understand the characters confidence and the risks he is willing to take to complete a job. This confidence is a reflection of the coming actions later in the movie. '
          },
          {
            songTitle: 'Sea Mine',
            movieName: 'Hot Fuzz',
            videoSource: '../src/assets/Wright/HotFuzz.mp4',
            description: 'This scene provides information in a comedic style, and sets up future action (ie. Our characters will use these weapons later. The use of jump-cuts to show the guns is effective and entertaining and of course jarring, as opposed to just a regular shot of showing the room. The recall ammunition sounds within the jump cuts are amplified as a hint that this scene important. '
          },
          {
            songTitle: 'Don\'t Stop Me Now',
            movieName: 'Shaun of the Dead',
            videoSource: '../src/assets/Wright/SotDTwo.mp4',
            description: 'Editing music to the beat of action, this is effective for comedic relief'
          },
        ]
      }
    },
    methods: {
      playToggle() {
        this.isPlaying = !this.isPlaying
      },
      next() {
        if (this.currentIndex >= this.songs.length) {
          this.currentIndex = 0
        } else {
          this.currentIndex = this.currentIndex + 1
        }
        console.log('next', this.currentIndex)
      },
      previous() {
        if (this.currentIndex <= 0) {
          this.currentIndex = this.songs.length
        } else {
          this.currentIndex = this.currentIndex - 1
        }
        console.log('previous', this.currentIndex)
      }
 },
};
</script>

<style scoped lang="scss">
  .wright {
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
    display: flex;
    justify-content: space-between;
    flex-direction: column;
    padding: 2em 10em;
    height: 40vh;
  }
  .description {
    align-self: flex-end;
    margin-top: 5em;
    padding: 2em;
    display: flex;
    justify-content: center;
    width: 100%;
    &-body {
      width: 60%;
      font-size: 18px;
      color: white;
      text-align: center;
    }
  }
  .player {
    display: flex;
    justify-content: center;
    width: 950px;
    height: 270px;
    position: relative;
    margin-top: 3em;
    &-title {
      position: absolute;
      background: #DFDFDF;
      width: 90%;
      height: 100%;
      bottom: 2em;
      z-index: 1;
    }
    &-controls {
      z-index: 2;
      width: 100%;
      margin-top: 7em;
      background-color: white;
      display: flex;
      justify-content: center;
      height: 250px;
      box-shadow: 7px 0px 20px rgba(255, 255, 255, 0.25);
    }
    &-image {
      display: flex;
      justify-content: space-between;
      flex-direction: row;
      align-self: flex-start;
      width: 260px;
      height: 260px;
      background-color:#2B2B31;
      margin-top: -10%;
      box-shadow: 3px 20px 20px rgba(0, 0, 0, 0.3)
    }
    &-buttons {
      margin: 70px -80px 0 80px;
    }
    &-button {
      margin: 0 3em;
      cursor: pointer;
      border: none;
    }
  }
  .songs {
    display: flex;
    flex-direction: column;
    position: absolute;
    left: 350px;
    top: 50px;
    text-align: left;
    &-title {
      font-size: 14px;
      color: #949494;
      line-height: 3em;
    }
    &-movie {
      color: #2B2B31;
      line-height: 0em;
      font-weight: bold;
      font-size: 18px;
    }
  }
  .material-icons {
    font-family: 'Material Icons';
    font-weight: normal;
    font-size:80px;
    font-style: normal;
    color:#2B2B31;
    display: inline-block;
  }
</style>
