

<div class="endng">
    <h1 class="heading"><span>E</span><span>N</span><span>D</span><span>A</span><span>N</span><span>G</span><span>E</span><span>R</span><span>E</span><span>D</span></h1>
    <p class="par">The western black rhinoceros (Diceros bicornis longipes) or West African black rhinoceros is an extinct subspecies of the black rhinoceros. It was declared extinct by the IUCN in 2011.
        Read more about it at <a class="wiki" href="https://en.wikipedia.org/wiki/Western_black_rhinoceros">Wikipedia</a>
    </p>
</div>

<style>
    @keyframes glow {
        0% {
            box-shadow: 0 0 5px 2px rgba(255, 255, 255, 0.2);
            background-color: rgb(29, 65, 29);
        }
        50% {
            box-shadow: 0 0 20px 5px rgba(255, 255, 255, 0.8);
            background-color:  rgb(72, 168, 72);
        }
        100% {
            box-shadow: 0 0 5px 2px rgba(255, 255, 255, 0.2);
            background-color: rgb(29, 65, 29);
            color: white;
        }
    }
    @keyframes glowText {
        0% {
            text-shadow: 0 0 5px rgba(255, 255, 255, 0.2);
            color: white;
        }
        50% {
            text-shadow: 0 0 20px rgba(255, 255, 255, 0.8);
            color:skyblue;
        }
        100% {
            text-shadow: 0 0 5px rgba(255, 255, 255, 0.2);
            color: white;
        }
    }
    
    .endng{
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        background-color: rgb(29, 65, 29);
        margin-top: 50px;
        animation: glow 4s infinite;
    }

    .heading{
        font-size: 3rem;
        display: flex;
        gap: 15px;
        color: darkkhaki;
        font-family: 'Phantom Sans', sans-serif;
        margin-bottom: 10px;
        animation: glowText 3s infinite;
    }
    .heading span:hover{
        color: red;
        transition: transform 0.6s ease-in-out;
        transform: rotate(360deg);
    }

    .par{
        color: white;
        font-size: 1.5rem;
        width: 65%;
        text-align: center;
        font-family: 'Phantom Sans', sans-serif;
        animation: glowText 3s infinite;
    }
    .wiki{
        display: inline-block;
        transition: transform 0.3s ease-in-out;
        color: white;
        text-decoration: underline;
    }
    .wiki:hover{
        color: blue;
        text-decoration: none;
        cursor: pointer;
        transform: scale(1.1);
    }
</style>