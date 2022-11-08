<template>
    <div class="area" >
        <ul class="circles">
                    <li></li>
                    <li></li>
                    <li></li>
                    <li></li>
                    <li></li>
                    <li></li>
                    <li></li>
                    <li></li>
                    <li></li>
                    <li></li>
            </ul>
    </div>
  <div class="wrapper">
    <div class="main-container">
    <div class="container-one">
            <div class="profile">
                <img src="../assets/profilepic.png" alt="">
                <h2>Дмитрий Стариков</h2>
                 <p>Junior Frontend Developer</p>
            </div>
            <br>
        <div class="social-links">
            <h3>ПОЛЕЗНЫЕ ССЫЛКИ</h3>
            <br>
                <div class="link">
                    <a href="https://github.com/eraserhand" target="_blank"> 
                        <img src="../assets/github.png" alt="">
                        <p>GitHub</p>
                    </a>
                </div>
                <div class="link">
                    <a href="https://vk.com/vamfar" target="_blank">
                        <img src="../assets/vk.png" alt="">
                        <p>VK</p>
                    </a>
                </div>
                <div class="link">
                    <a href="https://t.me/tricky_fingaz" target="_blank">
                        <img src="../assets/telegram.png" alt="">
                        <p>Telegram</p>
                    </a>
                </div>
                <div class="link">
                    <a href="https://wa.me/79119189239" target="_blank">
                        <img src="../assets/whatsapp.png" alt="">
                        <p>WhatsApp</p>
                    </a>
                </div>
            
        </div>
    </div>
    <div class="container-two">
        <div class="about-me">
            <h1>Расскажу о себе</h1>
            <p><span class="type" style="--n:460">Год назад я начал интересоваться IT. Изучал азы разных языков программирования, прошёл курс CS50x. В конце концов 
                выбор пал на веб-разработку, и я делал первые простые сайты на HTML, CSS и JavaScript. Были паузы в обучении, но всё же хотел
                освоить новую профессию. Результат моей работы сейчас на экране. Этот сайт написан на Vue.js 3. 
                Конечно, есть над чем поработать, но я люблю писать код и решать новые задачи.</span>
            </p>
        </div>
        <br>
        <div class="technology-section">
            <h1>Мой стек веб-технологий</h1>
            <div class="logos">
                <img src="../assets/JavaScript.png" alt="">
                <img src="../assets/html.png" alt="">
                <img src="../assets/CSS.png" alt="">
                <img src="../assets/vue.png" alt="">
                <img src="../assets/nodejs.png" alt="">
            </div>
        </div>
        <br>
        <div class="project-card" v-for="(items, index) in projectData.ProjectsArray" v-bind:key="items">
            <h2>{{projectData.ProjectsArray[index].Title}}</h2>
            <img :src="projectData.ProjectsArray[index].Image" alt="">
        </div>
    </div>
  </div>
  </div>
  
</template>

<script>
import jsonData from "/projects.json"
export default {
    data(){
        return{
            projectData: jsonData
        }
    }
}
</script>

<style scoped>   
    .wrapper{
        display: flex;
        justify-content: center;
        padding:1%;
        margin-top: -4%;
        position: static;
        filter: drop-shadow(16px 16px 20px #787f90c1);

    }
    .main-container{
        display: flex;
        flex-direction: row;
        background-color: #c4c0c0;
        border-radius: 25px;
        width: 60%;
        background-color: #abdad7;
    }
    .container-one{
        border-collapse: inherit;
        border-spacing: 0 10px;
        text-align:center;
        background-color:#787f90c1;
        width: 15%;
        padding: 2.5%;
        border-radius: 25px;
        box-shadow: rgba(0, 0, 0, 0.229) 0px 3px 8px;
        
    }
    .profile img{
        height: 8rem;
        border-radius: 25px;
        
    }

    .profile h2{
        display:table-row-group;
        text-align:center;
        font-size: 1.6rem;
        width: 0;
    }
    .profile p {
        display:table-row-group;
        text-align:center;
        font-size: 1.2rem;
        width: 0;
    }
    .social-links h3 {
        clear: both;
        display: inline-block;
        overflow: hidden;
        white-space: nowrap;
        text-align: center;
        margin-left: -19px;
        font-size:1.27em;
        color:black;
    }

    .link a {
        text-decoration: none;
        color: #090707fa;
        font-size: 16px;
        font-weight:bolder;
    }
    .link img{
        mix-blend-mode: multiply;
        height: 2.4rem;
        transition:transform 0.25s ease;

    }
    .link img:hover {
        -webkit-transform:scale(1.8);
        transform:scale(1.8);
    }
    .container-two{
        margin: 2.5%;
        width: 85%;
        color: rgb(0, 0, 0);
    }
    .about-me{
        position: static;
        height: 32%;
        text-align: left;
        font-size:20px;
        color:black;
    }
    .about-me h1 {
        visibility: hidden;
        margin:2%;
        padding-left:5%;
        overflow: hidden; 
        border-right: .15em solid transparent ; 
        white-space: nowrap;
        animation: 
        typing 1s steps(30, end) forwards,
        blink-caret .85s step-end .75;
        animation-delay:.5s;   
}
    @keyframes typing {
        from { visibility: visible; width: 0 }
        to { visibility: visible; width: 80% }
    }

    @keyframes blink-caret {
        100% { border-color: transparent }
        50% { border-color: black }
    }
    .about-me p {
        text-indent: 5%;
        text-align: justify;
        margin: 2%;     
    }
    .type {
        visibility: hidden;
        overflow:hidden;
        font-family: monospace;
        color:#0000;
        background:
            linear-gradient(-90deg,#000000 5px,#0000 0) 10px 0,
            linear-gradient(#000000 0 0) 0 0;
        background-size:calc(var(--n)*1ch) 200%;
        -webkit-background-clip:padding-box,text;
        background-clip:padding-box,text;
        background-repeat:no-repeat;
        animation: 
            b .7s infinite steps(1),   
            t calc(var(--n)*.050s) steps(var(--n)) forwards;
            animation-delay:1.75s;
            
    }
    @keyframes t{
    from { background-size:0 200%;visibility:visible }
    100% { visibility:visible }
    }
    @keyframes b{
    50% {background-position:0 -100%,0 0;}
    }
    .technology-section {
        width:70%;
        height:17%;
        margin-left:auto;
        margin-right: auto;
    }
    .technology-section h1 {
        text-align:center;
        margin-top: 3%;
    }
    .logos img{
        height: 4.5rem;
    }
    
    
    .project-card {
        text-align:center;
        position: relative;
        margin-left:auto;
        margin-right:auto;
        margin-bottom: 6px;
        flex-wrap: 0 0 40%;
        background-color: rgba(0, 0, 0, 0.253);
        border-radius: 25px;
        box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
        height: 19.5rem;
        width: 19rem;
        color:white;
    }
    .project-card h2 {
        color: black;
        margin-top:3px;
    }
    .project-card img {
        margin-top:-6px;
        height: 14rem;
        justify-content: center;
        border-radius: 25px;
        box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
        transition:transform 0.25s ease;
    }
    .project-card img:hover {
        -webkit-transform:scale(1.55);
        transform:scale(1.55);
    }
    .area{
    background: #7fb3bb;  
    background: -webkit-linear-gradient(to left, #8fedfb, #7fb3bb); 

}

.circles{
    position: inherit;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    overflow: hidden;
}

.circles li{
    position: absolute;
    display: block;
    list-style: none;
    width: 20px;
    height: 20px;
    background: rgba(128, 16, 16, 0.2);
    animation: animate 15s linear infinite;
    bottom: -150px;
    
}

.circles li:nth-child(1){
    left: 25%;
    width: 80px;
    height: 80px;
    animation-delay: 0s;
}

.circles li:nth-child(2){
    left: 10%;
    width: 20px;
    height: 20px;
    animation-delay: 0s;
    animation-duration: 12s;
}
.circles li:nth-child(3){
    left: 70%;
    width: 20px;
    height: 20px;
    animation-delay: 0s;
}
.circles li:nth-child(4){
    left: 40%;
    width: 60px;
    height: 60px;
    animation-delay: 0s;
    animation-duration: 18s;
}
.circles li:nth-child(5){
    left: 65%;
    width: 20px;
    height: 20px;
    animation-delay: 0s;
}
.circles li:nth-child(6){
    left: 75%;
    width: 110px;
    height: 110px;
    animation-delay: 0s;
}
.circles li:nth-child(7){
    left: 35%;
    width: 150px;
    height: 150px;
    animation-delay: 0s;
}
.circles li:nth-child(8){
    left: 50%;
    width: 25px;
    height: 25px;
    animation-delay: 0s;
    animation-duration: 45s;
}
.circles li:nth-child(9){
    left: 20%;
    width: 15px;
    height: 15px;
    animation-delay: 0s;
    animation-duration: 35s;
}

.circles li:nth-child(10){
    left: 85%;
    width: 150px;
    height: 150px;
    animation-delay: 0s;
    animation-duration: 11s;
}
.circles li:nth-child(11){
    left: 15%;
    width: 90px;
    height: 90px;
    animation-delay: 0s;
    animation-duration: 11s;
}
.circles li:nth-child(12){
    left: 25%;
    width: 120px;
    height: 120px;
    animation-delay: 0s;
}
.circles li:nth-child(13){
    left: 15%;
    width: 130px;
    height: 130px;
    animation-delay: 0s;
}
.circles li:nth-child(14){
    left: 22%;
    width: 100px;
    height: 100px;
    animation-delay: 0s;
}
.circles li:nth-child(15){
    left: 35%;
    width: 95px;
    height: 95px;
    animation-delay: 0s;
}
.circles li:nth-child(16){
    left: 17%;
    width: 80px;
    height: 80px;
    animation-delay: 0s;
}
.circles li:nth-child(17){
    left: 44%;
    width: 100px;
    height: 100px;
    animation-delay: 0s;
}
.circles li:nth-child(18){
    left: 5%;
    width: 130px;
    height: 130px;
    animation-delay: 0s;
}
.circles li:nth-child(19){
    left: 11%;
    width: 115px;
    height: 115px;
    animation-delay: 0s;
}

@keyframes animate {

0%{
    transform: translateY(0) rotate(0deg);
    opacity: 1;
    border-radius: 0;
}

100%{
    transform: translateY(-1000px) rotate(720deg);
    opacity: 0;
    border-radius: 50%;
}

}

    @media only screen and (max-width: 950px) {
        .main-container {
            width: 95%;
        }
    }
</style>
