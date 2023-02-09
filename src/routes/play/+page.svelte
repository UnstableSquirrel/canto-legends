<script lang="ts">

    let src :string = "/img/anim/empty.png"
    // const timeout = setTimeout(effect2, 1000);
    // function stop() {
    //     clearTimeout(timeout);
    // }

    // const timeout = setTimeout(effect2, 1000);
    // clearTimeout(timeout)

    let anim :string = "effect 0s linear 0s 1;"

    function effect() {
        anim = "effect 1.5s linear 0s 1;"
        // const timeout = setTimeout(effect2, 1000);
        // clearTimeout(timeout)
    }

    function effect2() {
        anim = ""
    }

</script>

    <section>
        <div>
            <div class="top">
                <div class="card-container-top">
                    <p>100%</p>
                    <div class="health-bar-top">
                        <div></div>
                    </div>
                    <img src="/img/cards/card2.png" alt="Reelith">
                    <div style="{anim}" id="effect"></div>
                </div>
            </div>

            <div class="bottom">
                <div class="card-container-bottom" on:click="{effect}" on:keypress="{effect}">
                    <img src="/img/cards/card1.png" alt="Reelith">
                    <div style="animation: {anim}" id="effect"></div>
                    <div class="attack-bottom">
                        <div>Rage Strike</div>
                        <div>Water Punch</div>
                        <div>Meditation</div>
                        <div>Sword Attack</div>
                    </div>
                    <p>100%</p>
                    <div class="health">
                        <div class="health-bar-bottom">
                            <div></div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
<style>
    section {
        background-image: url("img/11.png");
        display: grid;
        justify-items: center;
        align-items: center;
        width: fit-content;
        width: 100%;
        height: 100vh;
        background-image: url("/img/11.png");
        background-repeat: no-repeat;
        background-size: cover;
        margin-top: 0em;
    }

    section > div {
        display: grid;
        justify-items: flex-start;
        align-items: baseline;
        height: 100vh;
    }

    section > div > .top {
        background-image: url("img/20.png");
        background-size: cover;
        display: grid;
        justify-items: center;
        align-items: center;
        width: 25em;
        height: 15em;
        width: 45em;
        height: 15em;
        border-radius: 2.5em;
        margin-bottom: auto;
    }

    section > div > .top > .card-container-top {
        position: relative;
        width: 220px;
        height: 300px;
        width: 250px;
        height: 350px;
        background-color: #06093a;
        border-radius: 2em;
        margin-top: 0em;
    }

    section > div > .top > .card-container-top > p {
        font-size: 1.7em;
        font-weight: 700;
        text-align: center;
        text-shadow: 1px 1px 5px#06093a;
        margin: 0px;
        padding: 0px;
        z-index: 2;
        position: absolute;
        top: 0%;
        left: 44%;
    }

    section > div > .top > .card-container-top > .health-bar-top {
        width: 200px;
        height: 25px;
        background-color: rgb(2, 161, 161);
        border: 1px solid blueviolet;
        box-shadow: 1px 1px 5px 1px blueviolet;
        margin: 0px;
        padding: 0px;
        z-index: 2;
        position: absolute;
        top: 9%;
        left: 10%;
        /* margin-bottom: -0.5em; */
    }

    section > div > .top > .card-container-top > .health-bar-top > div {
        width: 200px;
        height: 25px;
        background-color: aqua;
        margin: 0px;
        padding: 0px;
        color: #06093a;
    }

    section > div > .top > .card-container-top > img {
        position: absolute;
        bottom: -2%;
        left: 6.5%;
        width: 220px;
        height: 300px;
    }

    section > div > .bottom {
        background-image: url("img/20.png");
        background-size: cover;
        display: grid;
        justify-items: center;
        align-items: center;
        width: 25em;
        height: 15em;
        width: 45em;
        height: 15em;
        border-radius: 2.5em;
        margin-top: auto;
    }

    section > div > .bottom > .card-container-bottom {
        position: relative;
        width: 220px;
        height: 300px;
        width: 250px;
        height: 450px;
        background-color: #06093a;
        border-radius: 2em;
        margin-top: -13em;
    }

    section > div > .bottom > .card-container-bottom > img {
        position: absolute;
        top: -2%;
        left: 6.5%;
        width: 220px;
        height: 300px;
        /* width: 300px;
        height: 420px; */
    }

    section > div > .bottom > .card-container-bottom >.attack-bottom {
        display: grid;
        justify-items: center;
        align-content: center;
        grid-template-columns: auto auto;
        position: absolute;
        bottom: 16%;
        left: 7.5%;
    }

    section > div > .bottom > .card-container-bottom >.attack-bottom > div {
        display: grid;
        justify-items: center;
        align-content: center;
        background-color: rgb(19, 19, 19);
        border: 1px solid blueviolet;
        box-shadow: 1px 1px 7px 1px blueviolet;
        font-size: 1.2em;
        width: 100px;
        height: 35px;
        margin: 5px;
    }

    section > div > .bottom > .card-container-bottom >.attack-bottom > div:hover {
        background-color: #02a1a1;
        cursor: pointer;
        transition: all 0.3s ease-in-out;
    }

    section > div > .bottom > .card-container-bottom > .health {
        display: grid;
        justify-items: center;
        align-items: center;
        margin: 0px;
        padding: 0px;
        position: absolute;
        bottom: 5%;
        left: 11.5%;
    }

    section > div > .bottom > .card-container-bottom > p {
        font-size: 1.7em;
        font-weight: 700;
        text-align: center;
        text-shadow: 1px 1px 5px#06093a;
        margin: 0px;
        padding: 0px;
        z-index: 2;
        position: absolute;
        bottom: 9%;
        left: 44%;
    }

    section > div > .bottom > .card-container-bottom > .health > .health-bar-bottom {
        width: 200px;
        height: 25px;
        background-color: rgb(2, 161, 161);
        border: 1px solid blueviolet;
        box-shadow: 1px 1px 5px 1px blueviolet;
        margin: 0px;
        padding: 0px;
        z-index: 2;
        margin-bottom: -0.5em;
    }

    section > div > .bottom > .card-container-bottom > .health > .health-bar-bottom > div {
        width: 200px;
        height: 25px;
        background-color: aqua;
        margin: 0px;
        padding: 0px;
        color: #06093a;
    }

    #effect {
        position: absolute;
        background-image: url("/img/anim/empty.png");
        /* background-image: url("/img/anim/LightCast_96.gif"); */
        background-size: cover;
        background-repeat: no-repeat;
        background-size: 100%;
        top: 25%;
        left: 20%;
        width: 60%;
        height: 50%;
        /* animation: effect 1.5s linear 0s 1; */
    }

    /* section > div > .bottom > .card-container-bottom > img:hover #effect {
        animation: effect 0.1s linear 0s infinite alternate;
    } */

    @keyframes effect {
        from {background-image: url("/img/anim/empty.png")}
        to {background-image: url("/img/anim/LightCast_96.gif")}
    }




</style>