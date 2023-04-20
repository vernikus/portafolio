<script setup>
    const props = defineProps({pathUrl:String,nameMedia:String,url:String})
</script>

<template>
    <li v-if="props.url">
        <a v-if="url != 'jonthan.enriquez.l@gmail.com'" :href="props.url"><img :src="`src/assets/Images/icon-${props.pathUrl}.png`" :alt="props.nameMedia"></a>
        <a v-else href="mailto:props.url"><img :src="`src/assets/Images/icon-${props.pathUrl}.png`" :alt="props.nameMedia"></a>
    </li>
    <li v-else>
        <a :href="props.url"><img :src="`src/assets/Images/icon-${props.pathUrl}.png`" :alt="props.nameMedia"></a>
    </li>
</template>

<style>

img{
    width: 30px;
    height: 30px;
}
.container-media > ul > li{
    position: relative;
    display: inline-block;
    padding: 12px 20px;
    margin-left:2px ;
    background-color: #fff;
}

.container-media > ul > li::before{
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    bottom: 0;
    right: 0;
    margin: -2px;
    border-radius: 3px;
    background: linear-gradient(90deg, rgba(2,0,36,1) 0%, rgba(27,255,45,0.9948354341736695) 0%, rgba(0,212,255,1) 100%);
    z-index: -10;
}
.container-media > ul > li:hover{
    background-color: #ecedf3;
}
</style>