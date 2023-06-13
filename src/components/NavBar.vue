<script setup>
import {ref,onMounted} from 'vue'

let spanBurger = undefined
let menu = undefined

onMounted(()=>{
    spanBurger = document.querySelectorAll('.burger')
    menu = document.querySelector('.menu')
})
const classAdd = () =>{
    spanBurger[0].classList.toggle('activate')
    spanBurger[1].classList.toggle('activate')
    spanBurger[2].classList.toggle('activate')
    menu.classList.toggle('activate')
}

</script>

<template>
        <nav>
            <div>
                <span>Michingon</span>
                <span class="line"></span>
            </div>
            <div class="burger-menu" @click="classAdd">
                <span class="burger "></span>
                <span class="burger "></span>
                <span class="burger "></span>
            </div>
            <ul class="menu">
                <li><a href="#header">Inicio</a><span></span></li>
                <li><a href="#tecnologias">Tecnologías</a><span></span></li>
                <li><a href="#proyectos">Proyectos</a><span></span></li>
            </ul>
        </nav>
</template>


<style scoped>

    nav{
        display: flex;
        justify-content: space-between;
        padding: 20px 0px;
        font-size: 30px;
        position: sticky;
        top: 0;
        background-color: white;
        z-index: 100;
    }

       div.burger-menu{
        display: none;
        cursor: pointer;
        width: 45px;
        height: 30px;
            
    }
    div.burger-menu > span{
        background: linear-gradient(90deg, rgba(2,0,36,1) 0%, rgba(27,255,45,0.9948354341736695) 0%, rgba(0,212,255,1) 100%);
        border-radius: 2px;
        height: 4px;
        width: 100%;
        display: block;
        margin-top: 8px;
        transform-origin: 0px 100%;
        transition:all .5s ;
    }
    div.burger-menu > span.activate:nth-child(1){
        transform: rotate(45deg)  translate(-2px, 1px);  
    }
    div.burger-menu > span.activate:nth-child(2){
    opacity: 0;
    }
    div.burger-menu > span.activate:nth-child(3){
        transform: rotate(-45deg)  translate(-4px, 4px);
    }
    ul.menu{
        display: flex;
        justify-content: space-around;
    }
    li{
        margin-right: 30px;
    }
    a{
        text-decoration: none;
    }
    li > span{
        background-color:#1bff2d;
        width: 0;
        display: block;
        height: 4px;
        margin-top: 5px;
        transition: .5s ease;
    }
    li:hover > span{
        background-color: #00d4ff;
        width: 100%;
        transition: 1s ease;
    }

    @media  screen and (max-width:800px) {
        ul.menu{
            flex-direction: column;
            align-items: center;
            position: absolute;
            top:-100vh;
            left: -100vw;
            opacity: 0;
            height: 100vh;
            width: 100%;
            background-color: #000000e6;
            transition: all .5s ease;
        }
        ul.activate{
            transition: all .5s ease;
            top: 83px;
            left: 0;
            border-radius: 0 0 250px 0;
            opacity: .9;
        }
        nav{
            padding: 20px 20px;
        }
        ul.menu > li{
            margin: 0;
        }
        ul.menu > li > a{
            color: #f2f2f2; 
        }
        div.burger-menu{
            display: block;
        }

    }
</style>