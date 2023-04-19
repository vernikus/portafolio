<script setup>
import Media from './Media.vue';
const props = defineProps(
    {title:String,
    pathUrl:String,
    text:String,
    technologies:Array,
    demo:String

    })

</script>


<template>
    <div class="container-info">
        <div>

            <h3>{{ props.title }}</h3>
            <slot></slot>
            <h3>Lenguajes y tecnologías</h3>
            <ul>
                <li
                v-for="tech in technologies"
                :key="tech"
                >{{ tech }}</li>
            </ul>
        </div>
        <img :src="`src/assets/Images/proyect-${props.pathUrl}.png`" alt="" >
    </div>
</template>


<style scoped>

    img{
        width: 300px;
        height: 300px;
    }
</style>

