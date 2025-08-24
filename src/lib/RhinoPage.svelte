<script>
    let paras=[];
    let src=["https://freegifimg.com/download/rhinos/569905-rhino-free-photo.gif","https://freegifimg.com/download/rhinos/569922-rhino-download-hd.gif","https://freegifimg.com/download/rhinos/569844-rhino-gif-file-hd.gif","https://freegifimg.com/download/rhinos/569817-rhino-hd-image-free.gif"]
</script>

<div class="content">
        <button class="return">return Home</button>
        <div class="container"><p class="para"></p></div>
        <p class="Clicknotice"><b>(Click on rhino to interact)</b></p>
</div>
<div class="rhino">
    <img class="image" src={src[0]} alt="">
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
        margin:5px 5px;
        cursor:pointer;
        border-radius:12px;
        transition: transform forwards;
    }
    .return:hover{
        background: #28882d;
        color:beige;
        transform: scale(1.1);
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