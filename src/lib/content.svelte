


<div class="content">
    <div class="written" >
        <h1 id=heading>
            <p class="head">
                Western Black Rhino
            </p>
        </h1>
        <h2 class="subheading">
            <slot name="subheading">
                {subhead}
            </slot>
        </h2>
        <slot>
            <p class="para">
                {para}
            </p>
        </slot>
        <div class="slider">
            <button class="prev" on:click={decrease}> <span class="material-symbols-outlined">
arrow_back_ios
</span> </button>
            <slot class="count"> {counter}/4 </slot>
            <button class="next" on:click={increase}> <span class="material-symbols-outlined">
arrow_forward_ios
</span> </button>
            
        </div>
    </div>
    <div class="photos"><img class="rhino" src={src} alt=""></div>
</div>

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
        width: 100vw;
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        margin: 10px;
        padding: 10px;
        gap: 5px;
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
    }
    .rhino
    {
        max-width: 100%;
        max-height: 100%;
        border-radius: 10px;
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        object-fit: cover;
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
</style>

<script>
    let src="https://wildlifevagabond.com/wp-content/uploads/2023/08/IMG_1376-2-Edit-2.jpg";
    let para ="The western black rhinoceros (Diceros bicornis longipes) is a subspecies of the black rhinoceros that was declared extinct by the International Union for Conservation of Nature (IUCN) in 2011. It was native to the savannas and grasslands of western and central Africa, particularly in countries such as Cameroon, Chad, and Nigeria.";
    let counter = 1;
    let subhead = "Area of Origin";
    function increase(){
        para="The western black rhinoceros was a herbivorous animal that primarily fed on a variety of vegetation, including leaves, shoots, fruits, and branches. It had a prehensile upper lip that allowed it to grasp and manipulate vegetation effectively. The diet of the western black rhino varied depending on the season and availability of food sources in its habitat.";
        counter = 2;
        subhead = "Diet";
    }
    function decrease(){
        para="The western black rhinoceros (Diceros bicornis longipes) is a subspecies of the black rhinoceros that was declared extinct by the International Union for Conservation of Nature (IUCN) in 2011. It was native to the savannas and grasslands of western and central Africa, particularly in countries such as Cameroon, Chad, and Nigeria.";
        counter = 1 ;
        subhead = "Area of Origin";
    }
</script>