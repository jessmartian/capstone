<template>
    <div class="wright">
        <div class="topbar"> Sound Effects </div>
            <div class="container">
                <div class="player">
                     <div class="player-title">
                     </div>
                     <div class="player-image">
                     </div>
                 </div>
                 <div class="discription">
                     <div class="discription-title">
                     </div>
                     <div class="discription-body">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc a fermentum magna. Suspendisse vitae ligula vitae diam imperdiet finibus. Integer interdum, dolor non pellentesque elementum, nulla mi commodo mauris, id tincidunt lectus dolor sit amet turpis. Donec diam mi, aliquam id v estibulum id, posuere eu tortor.</div>
                 </div>
             </div>
    </div>
</template>

<style scoped lang="scss">
    
    .wright {
        background-color: #2B2B31;
    }
    
    .topbar {
        text-align:left;
        font-size:2em;
        color: white;
        padding:2em 0 0 2em;
    
    }
    
    .container {
        background-color: #2B2B31;
        justify-content: space-between; 
        height: 40vh;
        width: 100%;
        height: 100%;
    }
    
    .player {
        background-color: #DFDFDF;
        display: flex;
        justify-content: center;
        align-content: center;
        margin: 7em auto;
        width: 850px;
        height: 270px;
        padding: 10px;
        
    }
    
    .player-title {
        background-color: white;
        position: absolute;
        display: flex;
        justify-content: center;
        margin: auto;
        width: 950px;
        height:250px ;
        top: 370px;
        box-shadow:4px 4px 20px black;
        
    }
    
    .player-image {
        position: absolute;
        width: 260px;
        height: 260px;
        background-color: pink;
    }
    
    .discription {
        border: white solid 3px;
        display: flex;
        justify-content: space-around;
        align-items: center;
        margin: 10em auto;
        width: 75%;
        padding: 0 70px;
    }
    
    .discription-body {
        display: flex;
        margin: auto;
        padding: 1em;
        font-size: 18px;
        color: white;
        
    }

</style>