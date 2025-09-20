
<script>
    import { Link } from "svelte-routing";

    

    let cards = ["https://wildlifevagabond.com/wp-content/uploads/2023/08/IMG_1376-2-Edit-2.jpg","https://images.squarespace-cdn.com/content/v1/5f1ab4309bd4b45e29ec3e4b/1620028456080-SYTABOMMEFAITUXE8F4I/black-rhino-eating.jpeg","https://a-z-animals.com/media/2022/02/shutterstock_1175506429.jpg","https://i2-prod.birminghammail.co.uk/incoming/article28580361.ece/ALTERNATES/s615/0_01HNYZE5FMMGR0XAZGVDJH89SS.jpg"];
    
    let paragraphs =["The western black rhinoceros (Diceros bicornis longipes) is a subspecies of the black rhinoceros that was declared extinct by the International Union for Conservation of Nature (IUCN) in 2011. It was native to the savannas and grasslands of western and central Africa, particularly in countries such as Cameroon, Chad, and Nigeria.","The western black rhinoceros was a herbivorous animal that primarily fed on a variety of vegetation, including leaves, shoots, fruits, and branches. It had a prehensile upper lip that allowed it to grasp and manipulate vegetation effectively. The diet of the western black rhino varied depending on the season and availability of food sources in its habitat.","The word “longipes” is of Latin origin, combining longus (“far, long”) and pēs (“foot”). This refers to the subspecies’ long distal limb segment, one of many special characteristics of the subspecies. Other distinct features of the western black rhino included the square based horn, first mandibular premolar retained in the adults, simple formed crochet of the maxillary premolar, and premolars commonly possessed crista.","The western black rhinoceros was a solitary animal, typically only coming together with other rhinos for mating purposes. It had a gestation period of approximately 15 months, after which a single calf was born. The calf would stay with its mother for up to three years before becoming independent."];
    let para=$state(paragraphs[0]);
    let counter = $state(1);
    let headings = ["Area of Origin","Diet","Physical Characteristics","Behavior and Reproduction"];
    let count=1;
    let visible = $state("none");
    let activeCard = 0;
    let animating = $state("");
    let card1 = $state()
    let zClasses = ["z-top","z-mid","z-low","z-back"];
    
    let subhead = $state(headings[0]);
    function increase(){
        console.log(card1);
        if(counter==3){
            visible="block";
        }
        if(counter===4){
            
            counter=0;
        }
        counter+= 1;
        para=paragraphs[counter-1];
        
        subhead = headings[counter-1];
        toggleCards();
    }
    function decrease(){
        if(counter===1){
            counter=5;
        }
        counter -= 1 ;
        para=paragraphs[counter-1];
        subhead = headings[counter-1];
        toggleCards();
    }

    function toggleCards() {
        animating = `card${activeCard + 1}-push card${(activeCard + 1)%cards.length + 1}-bring`;

        activeCard = (activeCard + 1) % cards.length;
        
        setTimeout(() =>{
         animating = "";
         zClasses= rotateArray(zClasses); 
        },1500);
    }

    function rotateArray(arr) {
    let newArr = [...arr]; 
    newArr.unshift(newArr.pop()); 
    return newArr;
    }
</script>


<div class="content">
    <div class="written" >
        <h1 id=heading>
            <p class="head">
                Western Black Rhino
            </p>
        </h1>
        <h2 class="subheading">
            
                {subhead}
            
        </h2>
        
            <p class="para">
                {para}
            </p>
        
        <div class="slider">
            <button class="prev" onclick={decrease}> <span class="material-symbols-outlined">
arrow_back_ios
</span> </button>
            <slot class="count"> {counter}/4 </slot>
            <button class="next" onclick={increase}> <span class="material-symbols-outlined">
arrow_forward_ios
</span> </button>
            
        </div>
    </div>
    <div class="photos">
    {#each cards as card, i}
      <img
        src={card}
        alt="card"
        class="cards {zClasses[i]}
          {animating.includes(`card${i+1}-push`) ? 'animate-pushBack' : ''}
          {animating.includes(`card${i+1}-bring`) ? 'animate-bringForward' : ''}"
      />
    {/each}
  </div>
    
</div>
<Link to="/Squishy">
<button class="play {visible.includes("block") ? 'visible' : 'hidden'} ">
        Ready to play with Squishy the Rhino? 
    </button>
</Link>

<style>
    @font-face {
        font-family: 'Phantom Sans';
        src: url('https://assets.hackclub.com/fonts/Phantom_Sans_0.7/Bold.woff')
            format('woff'),
            url('https://assets.hackclub.com/fonts/Phantom_Sans_0.7/Bold.woff2')
            format('woff2');
        font-weight: bold;
        font-style: normal;
        font-display: swap;
    }
    .content {
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        padding: 10px;
        gap: 5px;
        margin-top:10vh;
    }
    .para{
        padding: 10px;
        border: 4px dashed brown;
        border-radius: 10px;
        text-align: center;
    }
    .written {
        flex: 1;
        max-width: 60vw;
        padding: 20px;
        font-family: 'Phantom Sans', sans-serif;
        font-size: 1.5rem;
        line-height: 1.2;
        color: #333;
        border: 3px dotted red;
        border-radius: 10px;
    }
    #heading {
        font-size: 2.5rem;
        color:cadetblue;
        margin-bottom: 4px;
        text-decoration: underline;
    }
    .head {
        margin: 0;
    }
    .subheading {
        font-size: 2rem;
        color: #666;
        margin-bottom: 5px;
    }
    .photos {
        flex: 1;
        justify-content: center;
        align-items: center;
        height: 60vh;
        width: 30vw;
        padding: 10px;
        position: relative;
    }
    .cards
    {
        height: 60vh;
        width: 40vw;
        border-radius: 10px;
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        object-fit: cover;
        position: absolute;
    }
    @keyframes pushBack {
       0% { transform: translateX(-20px) translateY(10px) rotate(-5deg) scale(1); }
       50% { transform: translateX(-80px) translateY(150px) rotate(-45deg) scale(0.3); }
       100% { transform: translateX(-20px) translateY(10px) rotate(-5deg) scale(1); z-index: -1;
    }
   }
   @keyframes bringForward {
       0% { transform: translateX(0px) translateY(0px) scale(1); }
       50% { transform: translateX(40px) translateY(-50px) rotate(15deg) scale(1.05); }
       100% { transform: tranaslteX(20px) translateY(-10px) rotate(5deg) scale(1); z-index: 2;
    }
}

.animate-pushBack{ animation: pushBack 1.5s ease-in-out forwards;}
.animate-bringForward{ animation: bringForward 1.5s ease-in-out forwards;}
    #card1 {
        transform: translateX(-20px) translateY(10px) rotate(-5deg);
        z-index: 1;
        
    }
    #card2 {
        transform: translateX(20px) translateY(-10px) rotate(5deg);
        z-index: 0;
        
    }

    #card3 {
        transform: translateX(20px) translateY(-10px) rotate(15deg) scale(0.9);
        z-index: -1;
        
    }

    #card4 {
        transform: translateX(20px) translateY(-10px) rotate(25deg) scale(0.9);
        z-index: -2;
        
    }
    .z-top{
        z-index: 2;
    }
    .z-mid{
        z-index: 1;
    }
    .z-low{
        z-index: 0;
    }
    .z-back{
        z-index: -1;
    }

    .slider {
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 30px;
        margin-top: 20px;
    }
    .prev, .next {
        display: flex;
        background-color: #4CAF50;
        border: none;
        color: white;
        padding: 10px 20px;
        text-align: center;
        text-decoration: none;
        font-size: 16px;
        margin: 4px 2px;
        cursor: pointer;
        border-radius: 5px;
        transition: background-color 0.3s ease;
    }
    .prev:hover, .next:hover {
        background-color: #28882d;
        color: yellow;
    }
    .play{
        display: block;
        margin: 20px auto;
        background-color: orange;
        border: none;
        color: white;
        padding: 15px 30px;
        text-align: center;
        text-decoration: none;
        font-size: 2rem;
        cursor: pointer;
        border-radius: 8px;
        transition: background-color 0.3s ease;
    }
    @keyframes shake{
        0% { transform: translate(1px, 1px) rotate(0deg); }
        10% { transform: translate(-1px, -2px) rotate(-1deg); }
        20% { transform: translate(-3px, 0px) rotate(1deg); }
        30% { transform: translate(3px, 2px) rotate(0deg); }
        40% { transform: translate(1px, -1px) rotate(1deg); }
        50% { transform: translate(-1px, 2px) rotate(-1deg); }
        60% { transform: translate(-3px, 1px) rotate(0deg); }
        70% { transform: translate(3px, 1px) rotate(-1deg); }
        80% { transform: translate(-1px, -1px) rotate(1deg); }
        90% { transform: translate(1px, 2px) rotate(0deg); }
        100% { transform: translate(1px, -2px) rotate(-1deg); }
    }
    .play:hover {
        background-color: darkorange;
        color: yellow;
        animation: shake 0.5s ease-in-out infinite;
    }
    .hidden{
        display:none;
    }
    .visible{
        display:block;
    }
</style>
