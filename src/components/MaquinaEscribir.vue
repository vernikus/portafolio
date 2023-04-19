<script setup>
import { onMounted,ref } from 'vue';    
const textAnimate = [
  'Hola reclutador!!',
  '¿Como te puedo ayudar?',
  'Bienvenido a mi portafolio'
]

const messageIndex = ref(0)
const message = ref([])
const span = ref(undefined)
const count = ref(0)

const animateMessage = () =>{
    message.value =  textAnimate[messageIndex.value].split('')
    span.value = document.getElementsByClassName('typing')[0]
    span.value.innerHTML = ''
    let textLength = textAnimate[messageIndex.value].length
    setInterval(()=>{
        if (count.value === message.value.length) {
            span.value.innerHTML = textAnimate[messageIndex.value].substring(0,textLength)
            textLength--
        if (textLength === 0) {
            span.value.innerHTML = ''
            count.value = 0
            messageIndex.value == 2 ? messageIndex.value = 0 : messageIndex.value++
            textLength = textAnimate[messageIndex.value].length
            message.value = textAnimate[messageIndex.value].split('')
        }
        } else {
            span.value.innerHTML += message.value[count.value]
            count.value++
        }
    }, 150)


}

    onMounted(()=>{
        animateMessage()
    })

</script>

<template>
    <div class="container-print">
        <span class="typing"></span>
    </div>
</template>

<style scoped>
div{
    padding: 50px;
}
span.typing{
    letter-spacing: 10px;
    font-size:60px;
    border-right: .15em solid #414552;
    animation: blink .5s infinite step-end alternate;
}

@keyframes blink{
    50%{border: transparent;}
}
</style>