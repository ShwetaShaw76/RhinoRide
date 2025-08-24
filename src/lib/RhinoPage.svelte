<script>
    import { Link } from "svelte-routing";

    let paras=["Squishy is eating peacefully,better not disturb him","Squishy is looking for thing that disturbed him","Squishy is constantly staring at you","On no!! Squishy is charging towards you"];
    let src=["https://freegifimg.com/download/rhinos/569905-rhino-free-photo.gif","https://freegifimg.com/download/rhinos/569844-rhino-gif-file-hd.gif","https://freegifimg.com/download/rhinos/569922-rhino-download-hd.gif","https://freegifimg.com/download/rhinos/569817-rhino-hd-image-free.gif"]
    let i=0;
    function changeImage(){
        i+=1;
        if(i==4){
            window.open("https://www.youtube.com/shorts/Yl271V-0s5M")
        }
    }
</script>

<div class="content">
       <Link to="/"> <button class="return">return Home</button></Link>
        <div class="container"><p class="para">{paras[i]}</p></div>
        <p class="Clicknotice"><b>(Click on rhino to interact)</b></p>
</div>
<div class="rhino" onclick={changeImage}>
    <img class="image" src={src[i]} alt="">
</div>

<style>
    .content{
        display:flex;
        flex-direction:column;
        justify-content:center;
        align-items:center;
    }
    .return{
        background:#4CAF50;
        border:none;
        color:white;
        padding:10px 10px;
        text-align:center;
        text-decoration:none;
        display:inline-block;
        font-size:2rem;
        margin:3px 3px;
        cursor:pointer;
        border-radius:12px;
        transition: transform forwards;
    }
    .return:hover{
        background: #28882d;
        color:beige;
        transform: scale(1.1);
    }
    .container{
        background:cornflowerblue;
        border: 2px solid blueviolet;
        border-radius: 15px;
        padding: 4px;
        font-weight: 800;
        color: crimson;
        animation: change 3s ease-in-out infinite;
    }
    @keyframes change{
        0%{background: cornflowerblue;border: 2px solid blueviolet;color: crimson;}
        50%{background: linear-gradient(to right,yellow,cornflowerblue);border: 2px solid blue;border-radius: 40px;color: brown;}
        100%{background:cornflowerblue;border: 2px solid blueviolet;color: crimson;}
    }
    .para{
        font-size:2rem;
    }
    .Clicknotice{
        font-size: 2rem;
        
    }

    .rhino{
        min-height:40vh;
        width: auto;
        display: flex;
        justify-content: center;
        align-items: center;
        
    }
    .image{
        min-height: 40vh;
        width: auto;
        border: 5px solid brown;
        border-radius: 15px;
        background-color: white;
    }
</style>