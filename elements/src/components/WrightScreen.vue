<template>
  <div class="wright">
    <div class="topbar"> Sound Effects </div>
      <div class="container">
          <div class="player-title">
            <div class="songs-title">Alabama Song</div>
            <div class="songs-movie">The World's End</div>
            <div class="player">
              <div class="player-image"></div>
              <div class="player-buttons">
                <i class="material-icons">fast_rewind</i>
                <i class="material-icons" style="font-size:90px;color:#2B2B31">play_arrow</i>
                <i class="material-icons">fast_forward</i>
              </div>
            </div>
          </div>
      <div class="description">
        <div class="description-body">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc a fermentum magna. Suspendisse vitae ligula vitae diam imperdiet finibus. Integer interdum, dolor non pellentesque elementum, nulla mi commodo mauris, id tincidunt lectus dolor sit amet turpis. Donec diam mi, aliquam id v estibulum id, posuere eu tortor.</div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'WrightScreen',
    data () {
        return {
        }
    },
    components: {
    }
  }
</script>

<style scoped lang="scss">
  .wright {
    background-color: #2B2B31;
  }  
  .topbar {
    text-align: left;
    font-size: 2em;
    color: white;
    padding: 2em 0 0 2em;  
  } 
  .container {
    background-color: #2B2B31;
    justify-content: space-between; 
    height: 40vh;
    width: 100%;
    height: 100%;
  }
  .description {
    display: flex;
    justify-content: space-around;
    align-items: center;
    margin: 10em auto;
    width: 50%;
    padding: 0 0px;
    &-body {
      display: flex;
      margin: auto;
      padding: 1em;
      font-size: 18px;
      color: white;
      text-align:center;  
    }
  }
  .player {
    background-color: white;
    position: absolute;
    display: flex;
    justify-content: center;
    margin: auto;
    width: 950px;
    height:250px ;
    top: 370px;
    box-shadow: 7px 0px 20px rgba(255, 255, 255, 0.25);
    &-title {
      background-color: #DFDFDF;
      display: flex;
      justify-content: center;
      align-content: center;
      margin: 7em auto;
      width: 850px;
      height: 270px;
      padding: 10px;  
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
      i {
        cursor: pointer;
      }
    }
  }
  .songs {
    &-title {
      line-height: 10;
      margin: 0;
      font-size: 14px;
      color: #949494;
      text-align: right;
      margin-right: 5%;
    }
    &-movie {
      color: #2B2B31;
      position: absolute;
      line-height: 1;
      font-weight: bold;
      margin-top: 35px;
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
    letter-spacing: 1em;
  }    
</style>