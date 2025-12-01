<script>
    import {base} from '$app/paths';
    import {users_store} from "$lib/user";
    import { onMount } from 'svelte';
    onMount(() => {
        if($users_store.length > 2){
            users = JSON.parse($users_store);
        }
    });

    let users = [];
    let name = ""
    let mail = ""
    let pass = ""

    function handleLogin(){
        const logging_in = users.filter(user => namn === user.username && pass === user.password)
        if(logging_in.length > 0){
            alert("Du har loggat in!")
        } else{
            alert("Fel användarnamn eller lösenord.")
        }
    }
    
    //function handleSubmit(){
       //alert("Inlog "+'\n'+name+'\n'+mail+'\n'+pass)
    //}

</script>

<main>
    <div class="container">
        <h1> Inloggning </h1>
        <form on:submit|preventDefault={handleSubmit}> 
            
            <label for="name">Namn:</label>
            <input type="text" id="name" bind:value={name}>

            <label for="mail">E-mail:</label>
            <input type="email" id="mail" bind:value={mail}>

            <label for="password">Lösenord:</label>
            <input type="password" id="password" bind:value={pass}>


            <input type="submit" value="Logga in">
            <p> Har du inget konto? <a href="{base}/register">Registrera!</a></p>
        </form>

    </div>
</main>

<style>

    .container{
        border: solid 5px rosybrown;
        border-radius: 10px;
        width: 35%;
        height: 80%;
        background-color: #3a2e3b;
        margin: auto;
        display: flex;

        flex-direction:column;
        align-items:center;
        justify-content:space-evenly;

        min-height: 500px;
        min-width: 300px;
    }   

    main{
        background-image: url("https://t4.ftcdn.net/jpg/05/21/65/59/360_F_521655929_N80d5GaCQJ2VP073PfTXJTe9mkvsNtHE.jpg");
        background-size: cover;
        width: 100%;
        height: 100%;
        padding: 5%;

        min-height: 500px;
        min-width: 500px;
    }
    
    form{
        display: flex;
        flex-direction: column;
        gap: 1rem;
    }
    
</style>