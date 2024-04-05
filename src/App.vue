<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import HeaderTopBar from './components/header/HeaderTopBar.vue'
import type HomeViewVue from './views/HomeView.vue';
import CardMenu from './components/album/cardMenu.vue'
import CardPrincipal from './components/principal/cardPrincipal.vue'
import Carousel from './components/ui/carousel/Carousel.vue';
</script>

<template>

    <div class="wrapper">
      <HeaderTopBar/> 
      <div class="flex flex-row">
        <CardMenu/>
       <CardPrincipal/>
      </div>

      <HomeViewVue></HomeViewVue>
      
    </div>

</template>


