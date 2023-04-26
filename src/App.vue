<script setup>
  import NavBar from './components/NavBar.vue'
  import Media from './components/Media.vue'
  import Proyect from './components/Proyect.vue'
  import MaquinaEscribir from './components/MaquinaEscribir.vue'
  import { technologies,media,proyects} from './data';


  
</script>

<template>
  <NavBar/>
  <header>
      <div class="container-name">
        <span>Hola me llamo</span>
        <div class="name">
          <h1>Jonathan Enriquez</h1>
          <span>(Michingon)</span>
        </div>
        <p>Soy un desarrollador frontend jr, en constante búsqueda de mejorar mis skills, 
        siempre dispuesto a tomar nuevos retos, tanto laborales como personales.</p>
      </div>
      <div class="container-media">
        <ul>
          <Media
          v-for="{pathUrl,nameMedia,url} in media"
          :key="pathUrl"
          :pathUrl="pathUrl"
          :nameMedia="nameMedia"
          :url="url"
          />
        </ul>
      </div>
      <MaquinaEscribir/>
  </header>
  
  <main>  
    <section class="container-technologies">
      <div class="about-me">
        <h2>Sobre mi</h2>
        <span class="line"></span>
        <p>Hola, soy Jonathan Desarrollador Web Fronted,
          enfocado en el desarrollo y diseño de sitios web, que se adapten a tus necesidades y soluciones tus problemas.
        </p>
        <p>
          Me gusta aprender cosas nuevas y practicar constantemente lo que aprendo, estudio diariamente para perfeccionarme y ampliar mis conocimientos.
        </p>
      </div>
      <div class="technologies">
        <h2>Tecnologías</h2>
        <span class="line"></span>
        <div class="container-media">
          <ul >
            <Media
            v-for="{pathUrl,nameMedia} in technologies"
            :key="pathUrl"
            :pathUrl="pathUrl"
            :nameMedia="nameMedia"
            />
          </ul>  
        </div>
      </div>
    </section>
    <section class="container-proyects">
      <h2>Proyectos</h2>
      <span class="line"></span>
      <Proyect
      v-for="{pathUrl,title,text,technologies,demo} in proyects"
      :key="pathUrl"
      :pathUrl="pathUrl"
      :title="title"
      :text="text"
      :technologies="technologies"
      :demo="demo"
      >
      <a :href="demo" target="_blank" class="demo">Demo</a>
      </Proyect>
    </section>
  </main>

  <footer>
    <div class="contact-contaier">
      <h2>Contacto</h2>
      <span class="line"></span>
      <span>Contactame para trabajar juntos</span>
    </div>
    <div class="container-media">
      <ul>
        <Media
        v-for="{pathUrl,nameMedia,url} in media"
        :key="pathUrl"
        :pathUrl="pathUrl"
        :nameMedia="nameMedia"
        :url="url"
        />
      </ul>
    </div>
    <span>© 2022-2023 | Jonathan Enriquez.</span>
  </footer>
</template>

<style>


</style>
