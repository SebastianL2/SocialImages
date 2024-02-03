<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import HeaderTopBar from './components/header/HeaderTopBar.vue'
import type HomeViewVue from './views/HomeView.vue';
</script>

<template>

    <div class="wrapper">
      <HeaderTopBar/> 
      <HomeViewVue></HomeViewVue>
      
    </div>

</template>


