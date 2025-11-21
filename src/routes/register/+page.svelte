<script>
    import {base} from '$app/paths';
    import {users_store} from "$lib/user";
    import { onMount } from 'svelte';
    onMount(() => {
        /*Check if has more then 2 characters*/
        if($users_store.length > 2){
            users = JSON.parse($users_store);
        }
    });
    
    let users = [];
    let colors = [{namn: "Röd", value: "red"}, {namn: "Orange", value: "orange"},{namn: "Gul", value: "yellow"},{namn: "Grön", value: "lightgreen"},{namn: "Blå", value: "lightblue"}, {namn: "Lila", value: "purple"}, {namn: "Violet", value: "violet"}, {namn: "Rosa", value: "pink"}]
    let color = "black"
    let name = ""
    let mail = ""
    let pass = ""
    
    const existing_user = users.filter(user => namn === user.username)

    if (existing_user.length > 0){
        alert("Användaren finns redan!")
    }

    function handleSubmit(){
        alert("Välkommen "+'\n'+name+'\n'+mail+'\n'+pass)
        let new_user = {username: name, password: password, email: email, color: color};
        users = [...users, new_user];
        $users_store = JSON.stringify(users);
    }
</script>

<main>
    <div class="container">
        <h1> Registrering </h1>
        <form on:submit|preventDefault={handleSubmit}> 
            <div style="width: 100px; height: 100px; border-radius: 50%; overflow:hidden; background-color:{color};"></div>

            <label for="name">Namn:</label>
            <input type="text" id="name" bind:value={name}>

            <label for="mail">E-mail:</label>
            <input type="email" id="mail" bind:value={mail}>

            <label for="password">Lösenord:</label>
            <input type="password" id="password" bind:value={pass}>

            <label for="color">Favoritfärg:</label>
            <select type="color" id="color" bind:value={color}>
                {#each colors as c}
                    <option value={c.value}>{c.namn}</option>
                {/each}
            </select>

            <input type="submit" value="Registrera">
            <p> Har du redan ett konto? <a href="{base}/login">Logga in!</a></p>

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