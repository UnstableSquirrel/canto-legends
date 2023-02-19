<script  lang="ts">
    import { onMount } from 'svelte';
    import { browser } from '$app/environment';
    import { defaultEvmStores as evm, web3, selectedAccount, connected, chainId, chainData } from 'svelte-web3';

    let y :number = 0;
	let bg :string = "rgba(0, 0, 0, 0)";

	const changeBg = () => {
		if (y > 50) {
			bg = "rgb(4 18 37)";
		}
		else {
			bg = "rgba(0, 0, 0, 0)";
		}
	}

    let menuBarOpen :boolean = false;
    let rotationSpan1 :string = "rotate(0deg)";
    let rotationSpan2 :string = "rotate(0deg)";
    let marginSpan2 :string = "5px";
    let opacitySpan3 :string = "1";
    let sideBar :string = "0%";

    function toggleMenu() {
        if(!menuBarOpen) {
            rotationSpan1 = "rotate(135deg)";
            rotationSpan2 = "rotate(-135deg)";
            marginSpan2 = "-3px";
            opacitySpan3 = "0";
            sideBar = "100%";
            menuBarOpen = true;
            // console.log("open");
            return;
        }
        if(menuBarOpen) {
            rotationSpan1 = "rotate(0deg)";
            rotationSpan2 = "rotate(0deg)";
            marginSpan2 = "5px";
            opacitySpan3 = "1";
            sideBar = "0%";
            menuBarOpen = false;
            // console.log("closed");
            return;
        }
    }

    onMount(async () => {
		if(browser) {
			await evm.setProvider()
			// if ($chainId != 7700) {
			// 	alert("Please connect to the Polygon or BSC network.")
			// }
		}
	});

    function logout() {
        evm.disconnect()
    }

    export async function loginWithEth() {
        if(browser) {
            // Web3 provider
            // defaultEvmStores.setProvider('https://eth-mainnet.nodereal.io/v1/1659dfb40aa24bbb8153a677b98064d7')
            await evm.setProvider()
            // if ($chainId != 7700) {
            // 	alert("Please connect to the Canto network.")
            // }
        }
    }
    
</script>

    <svelte:window on:scroll={changeBg} bind:scrollY={y} />

    <div class="links-container2" style="width: {sideBar};">
        <div>
            <a href="/">Marketplace</a>
            <a href="/">Game Mechanics</a>
            <a href="/">Legends</a>
        </div>
    </div>
    <nav style="background: {bg};">
        <div class="links-container">
            <a href="/">Marketplace</a>
            <a href="/">Game Mechanics</a>
            <a href="/">Legends</a>
        </div>
        <div class="menu-button" on:click="{toggleMenu}" on:keypress="{toggleMenu}">
            <span style="transform: {rotationSpan1}; margin-top: 5px;"></span>
            <span style="transform: {rotationSpan2}; margin-top: {marginSpan2};"></span>
            <span style="opacity: {opacitySpan3}; margin-top: 5px;"></span>
        </div>
        {#if !$connected}
        <div class="login-button-container">
            <button on:click="{loginWithEth}">Connect</button>
        </div>
        {/if}
        {#if $selectedAccount}
        <div class="login-button-container">
            <button id="logout-button" on:click="{logout}">{$selectedAccount.slice(0, 4)}..{$selectedAccount.slice(38, 42)}</button>
        </div>
        {/if}
    </nav>

<style>

    nav {
        display: flex;
        position: fixed;
        justify-content: space-between;
        align-items: center;
        top: 0px;
        width: 80%;
        margin: 0;
        padding: 1em;
        border-radius: 10px;
        transition: all 0.5s linear;
        z-index: 5;
    }
    
    .menu-button {
        display: none;
        cursor: pointer;
        z-index: 5;
    }

    .menu-button > span {
        width: 30px;
        height: 2.5px;
        background-color: white;
        transition: all 0.2s linear;
    }

    .links-container2 {
        display: block; 
        position: fixed; 
        justify-content: center;
        align-items: center; 
        padding-top: 50px; 
        left: 0;
        top: 0;
        height: 100%; 
        overflow: auto;
        background-color: rgb(0, 0, 0);
        transition: all 0.2s linear;
        z-index: 4;
    }

    .links-container2 > div {
        display: grid; 
        justify-content: center;
        align-items: center; 
        font-size: 2em;
        margin-top: 200px;
    }

    .links-container2 > div > a {
        margin: 5px 0px 5px 0px;
        text-decoration: none;
        font-size: 1.5em;
        font-weight: 700;
        color: #f7d621;
    }

    .links-container2 > div > a:hover {
        color: #ffee8f;
    }

    .links-container {
        display: block;
    }

    .links-container > a {
        text-decoration: none;
        padding: 1em;
        font-size: 1.8em;
        font-weight: 700;
        color: #ffffff;
        /* -webkit-text-stroke: 0.7px rgb(255, 255, 255);
        text-stroke: 0.7px rgb(255, 255, 255); */
    }

    .login-button-container > button {
        max-width: 100px;
        max-height: 50px;
        justify-items: center;
        align-items: center;
        border: 1px solid black;
        color: #250abb;
        font-size: 1.8em;
        font-weight: 700;
        background: #f7d621;
        /* -webkit-text-stroke: 1px #250abb;
        text-stroke: 1px #250abb; */
    }

    #logout-button {
        max-width: 100px;
        max-height: 50px;
        justify-items: center;
        align-items: center;
        border: 1px solid black;
        color: #250abb;
        font-size: 1.4em;
        font-weight: 700;
    }

    button:hover {
      /* transform: translateY(-5px); */
      background: #ffffff;
      cursor: pointer;
      color: #1c050f;
      transition: all 0.3s;
    }

    #logout-button:hover {
      /* transform: translateY(-5px); */
      background: #ffffff;
      cursor: pointer;
      color: #1c050f;
      transition: all 0.3s;
    }

    @media (min-width: 0px) and (max-width: 830px) {
        nav {
            display: grid;
            justify-items: center;
            align-items: center;
            justify-content: center;
        }

        .menu-button {
            display: grid;
            margin-bottom: 25px;
        }

        .links-container {
            display: none;
        }

     }
</style>