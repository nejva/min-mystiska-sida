<script>
    import { fade } from 'svelte/transition'

    let varor = $state([{name:"Mjölk",purchased: false},{name:"Bröd",purchased: false},{name:"Smör",purchased: true}]);
    let current = $state("")

    function handleSubmit(){
        let new_vara = {name: current, purchased: false}
        if (new_vara.name <= 0){
            return
        }
        varor = [...varor, new_vara]
    }
    function handleRemove(i){
        varor.splice(i,1)
    }
    function handleTransfer(i){
        varor[i].purchased = ! varor[i].purchased
       
    }


</script>

<main class="container">
    <h1>Shoppinglist</h1>
    <div class="categories_container">
        <section>
            <h2>Varor att köpa</h2>
            <ol>
                {#each varor as vara,i}
                {#if !vara.purchased}
                    <li>
                        { vara.name }
                        <button onclick={()=>handleTransfer(i)}>Köpt?</button>
                        <button onclick={()=>handleRemove(i)}>Ta bort</button>
                    </li>
                    {/if}
                {/each}
            </ol>
        </section>

        <section>
            <h2>Köpta varor</h2>
            <ul>
                {#each varor as vara,i}
                {#if vara.purchased}
                    <li>
                        { vara.name }
                        <button onclick={()=>handleTransfer(i)}>Köpa igen?</button>
                        <button onclick={()=>handleRemove(i)}>Ta bort</button>
                    </li>
                    {/if}
                {/each}
            </ul>
        </section>
    </div>

    <form onsubmit={handleSubmit}>
        <input type="text" id="varan" bind:value={current} >
        <input type="submit" value="Lägg till">
    </form>
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
    .categories_container section:first-child h2{
        font-size: 25px;
        text-align: center;
        margin: 10px;
        padding: 10px;
        border-radius: 20px;
        background-color: rgba(147, 203, 203) 
    }
    .categories_container section:last-child h2{
        font-size: 25px;
        text-align: center;
        margin: 10px;
        padding: 10px;
        border-radius: 20px;
        background-color: rgb(137, 189, 189) 
    }

    ul{
        list-style-type: lower-alpha;
        list-style-position:inside
    }
    ol{
        list-style-type: circle;
        list-style-position:inside
    }
    li{
        border-bottom: 1px;
        border-color: white
    }

    input{
        border-radius: 20px;
        border-color:rgb(163, 179, 194)
    }

    button{
        margin: 5px;
        border-radius: 20px;
        border-color:rgb(163, 179, 194)
    }

    form{
        display: flex;
        flex-direction: column;
        gap: 0.5rem;
        width: 47%;
        margin: 10px;
        padding: 10px;
        border-radius: 20px;
        background-color: rgb(137, 189, 189) 
    }
</style>