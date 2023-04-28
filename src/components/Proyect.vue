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
            <h3> &lt{{ props.title }}/></h3>
            <div>
                <p>{{ text }}</p>
                <slot></slot>
            </div>
            <h3>Lenguajes y tecnologías</h3>
         
            <div class="container-media">
                <ul>
                    <Media
                    v-for="{pathUrl,nameMedia} in technologies"
                    :key="pathUrl"
                    :pathUrl="pathUrl"
                    :nameMedia="nameMedia"
                    />
                </ul>
            </div>
        </div>
        <img :src="`src/assets/Images/proyect-${props.pathUrl}.png`" alt="" >
    </div>
</template>


<style>

    .container-info  .container-media > ul > li{
        padding:7px 20px ;
        margin-right: 10px;
    }
    .container-info  .container-media > ul > li > a > img{
        width: 20px;
        height: 20px;
    }
    .demo{
        text-decoration: none;
        margin: 20px 0;
        padding: 7px 20px;
    }
    .container-info{
    display: grid;
    grid-template-columns: repeat(2,1fr);
    justify-items: center;
    margin: 50px 0;
}

.container-info  p{
    text-align: justify;
}
img{
    width: 300px;
    height: 300px
}
</style>

