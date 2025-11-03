<script> 
    let image = "https://i.pinimg.com/736x/13/4b/9b/134b9b934f0f6fba159d824a04947559.jpg"
    let photo = "https://preview.redd.it/help-me-find-this-exact-crying-cat-meme-v0-k9x8mkwkd8lc1.jpeg?width=360&auto=webp&s=e9d63e2c97d18164f0926ec9218ef9109edf9749"
    let picture = "https://en.meming.world/images/en/1/13/Thumbs_Up_Crying_Cat.jpg"
</script>

<h1> CatApp </h1>
<p> Denna sida innehåller fina katter. </p>

<div class="photos">
    <div class="image-wrapper">
        <img src={image} alt="kul katt">
    </div>
    <div class="image-wrapper">
        <img src={photo} alt="en till kul katt">
    </div>
    <div class="image-wrapper">
        <img src={picture} alt="ännu en till kul katt">
    </div>
</div>

<style>
    h1{
        text-align: center;
        font-size: 50px;
        margin: 20px;
        color: rgb(223, 195, 195);
    }
    p{
        text-align: center;
        font-size: 40px;
        margin: 20px;
        color: rgb(226, 212, 212);
    }

    .photos{
        display:flex;
        max-width: 90vw;
        flex-wrap: wrap;
        background-color: rgb(235, 223, 223);
        border-radius: 20px;
    }
    .photos{
        width: 100%;
        align-items:center;
        justify-content:center;
        max-height: 50vh ;

    }
    .image-wrapper{
        height: 40vh;
        flex:1;

    }
    .image-wrapper img{
        width: 100%; 
        margin:10px;
        border-radius: 20px;
        border: 2px solid white;
        box-shadow: 4px 8px 8px rgba(255, 0, 0, 0.2);
        height: 100%;
    }
    .image-wrapper:hover { 
        flex-grow:2; 
    }
    .image-wrapper:active { 
        transform: scale(0.9); 
    }
</style>