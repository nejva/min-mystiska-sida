<script>
    let cards = $state([{image: "https://en.meming.world/images/en/1/13/Thumbs_Up_Crying_Cat.jpg", flipped: false, matched: false}])
    let bluePoints = 0
    let redPoints = 0
    let blueTurn = true
</script>

<h1>Memory</h1>
<aside>
    <p>Points</p>
</aside>
<aside class="blue">
    <p>Points</p>
</aside>
<aside class="turn" class:blue= { blueTurn }></aside>

<main>
    {#each cards as card}
        <div class="card" class:flipped= { card.flipped }>
            <img src={cards.image} alt=framsida class="front">
            <img src={cards.image} alt=baksida class="back">
        </div>
    {/each}
</main>

<style>
    h1{
        text-align: center;
    }
    main{
        display:grid;
        grid-template-rows: repeat(3,100px);
        grid-template-columns: repeat(4,100px);
        justify-content: center;
    }
    .card{
        border: black 1px solid;
        height: 100%;
        width: 100%;
        position:relative;
        backface-visibility: hidden;
        transition: transform 0.5s;
    }
    aside{
        width: 100px;
        height: 100px;
        position: fixed;
        bottom: 10px;
        right: 10px;
        background-color: red;
        display: flex;
        justify-content: center;
        align-items: center;
  }
  .blue{
    left:10px;
    background-color:blue;
  }

  p{
    font-size: 30px;
  }
  .turn{
    box-shadow: 0 0 10px 10px yellowgreen;
    z-index: -1;
  }
  .front{
    transform: rotateY(180deg);
  }
</style>