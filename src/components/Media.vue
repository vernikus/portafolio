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

<style scoped>

    img{
        width: 30px;
        height: 30px;
    }
    
</style>