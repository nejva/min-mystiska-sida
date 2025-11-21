<script>

    let varor = $state([{ name:"Mjölk",  }]);

</script>
<main class="container">
    <h1>Shoppinglist</h1>
    <div class="categories_container">
        <section>
            <h2>Varor att köpa</h2>
            <ol>
                {#each varor as vara}
                    <li>
                        { vara.name }
                    </li>
                {/each}
                {#each varor as vara}
                    <li>
                        { vara.name }
                    </li>
                {/each}
            </ol>
        </section>
        <section>
            <h2>Köpta varor</h2>
            <ul>
                {#each varor as vara}
                    <li>
                        { vara.name }
                    </li>
                {/each}
                {#each varor as vara}
                    <li>
                        { vara.name }
                    </li>
                {/each}
            </ul>
        </section>
    </div>
</main>

<style>

    .container{
        background-color: rgb(196, 233, 234);
        width: 70vw;
        height: 90vh;
        border-radius: 20px;
        margin: auto;


        display: grid;
        grid-template-rows: 1fr 9fr 1fr;
    }
    .categories_container{
        display: grid;
        grid-template-columns:repeat(2,1fr);
        background-color: rgb(216, 238, 239);
        height: 100%;
        
        gap: 10px;
    }
    h1{
        background-color: rgb(147, 203, 203);
        border-radius: 20px;
    }
    .container h1{
        align-self:center;
        justify-self:center;
        padding: 8px;
    }
    .categories_container section:first-child{ 
        border-radius: 20px;
        background-color: rgb(206, 234, 235) 
    }
 
    .categories_container section:last-child{  
        border-radius: 20px;
        background-color: rgb(192, 222, 223) 
    }
    .categories_container section:last-child h2{
        font-size: 25px;
        text-align: center;
        margin: 10px;
        padding: 10px;
        border-radius: 20px;
        background-color: rgb(137, 189, 189) 
    }
    .categories_container section:first-child h2{
        font-size: 25px;
        text-align: center;
        margin: 10px;
        padding: 10px;
        border-radius: 20px;
        background-color: rgba(147, 203, 203) 
    }
    ul{
        list-style-type: lower-alpha;
        list-style-position:inside
    }
    ol{
        list-style-type: circle;
        list-style-position:inside
    }
</style>