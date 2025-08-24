<script>

let icons = ["sound_detection_loud_sound","no_sound"];
import sound from '/src/assets/the-sound-of-a-rhino-growling.mp3';
const audio = new Audio(sound);
let playing = false;
function playSound() {
    if(playing){
        playing=false;
        audio.pause();
        audio.currentTime = 0;
        return;
    }
    else{
        audio.play();
        playing=true;
        audio.onended=()=>{
            playing=false;
        }
    }
    
}
</script>

<svelte:head>
    <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined" />
</svelte:head>

<div class="button">
    <button onclick={playSound}><span class="material-symbols-outlined" id="icon">{icons[playing?0:1]}
</span>
    </button>
</div>

<style>
    .button{
        position: fixed;
        bottom: 75vh;
        right: 2vw;
        z-index: 1000;
    }
    button{
        background: #4CAF50;
        border:3px solid whitesmoke;
        color:white;
        padding:15px 15px;
        text-align:center;
        text-decoration:none;
        display:inline-block;
        font-size:2rem;
        margin:5px 5px;
        cursor:pointer;
        border-radius:50%;
        transition: transform forwards;
    }
    button:hover{
        background: #28882d;
        color:beige;
        transform: scale(1.1);
    }
    #icon{
        font-size:2.5rem !important;
        vertical-align: middle;
    }
</style>