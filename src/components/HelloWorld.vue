<script setup lang="ts">
import { Button } from '@/components/ui/button'

</script>

<template>
<nav class="bg-gray-800 shadow-lg">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="flex justify-between h-16">
      <div class="flex">
        <!-- Logo -->
        <div class="flex-shrink-0 flex items-center">
    
        </div>

        <!-- Enlaces del Navbar -->
        <div class="hidden sm:-my-px sm:ml-6 sm:flex sm:space-x-8">
          <router-link to="/about">
          <a  class="inline-flex items-center px-1 pt-1 border-b-2 border-transparent text-sm font-medium text-white hover:text-gray-100 hover:border-gray-300">Inicio</a>
        </router-link>
          <a  class="inline-flex items-center px-1 pt-1 border-b-2 border-transparent text-sm font-medium text-white hover:text-gray-100 hover:border-gray-300">Acerca de</a>
          <a  class="inline-flex items-center px-1 pt-1 border-b-2 border-transparent text-sm font-medium text-white hover:text-gray-100 hover:border-gray-300">Servicios</a>
          <a  class="inline-flex items-center px-1 pt-1 border-b-2 border-transparent text-sm font-medium text-white hover:text-gray-100 hover:border-gray-300">Contacto</a>
        </div>
      </div>

      <!-- Botón de Menú (Para pantallas pequeñas) -->
      <div class="-mr-2 flex items-center sm:hidden">
        <button type="button" class="inline-flex items-center justify-center p-2 rounded-md text-white hover:text-gray-100 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-white" aria-controls="mobile-menu" aria-expanded="false">
          <span class="sr-only">Abrir menú principal</span>
          <!-- Icono de hamburguesa para menú móvil -->
          <svg class="block h-6 w-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" aria-hidden="true">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16m-7 6h7"></path>
          </svg>
          <!-- Icono de X para cerrar menú móvil -->
          <svg class="hidden h-6 w-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" aria-hidden="true">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path>
          </svg>
        </button>
      </div>
    </div>
  </div>

  <!-- Menú móvil, muestra el contenido en pantallas pequeñas -->
  <div class="sm:hidden" id="mobile-menu">
    <div class="px-2 pt-2 pb-3 space-y-1">
      <a href="#" class="block px-3 py-2 rounded-md text-base font-medium text-white hover:text-gray-100 hover:bg-gray-700">Inicio</a>
      <a href="#" class="block px-3 py-2 rounded-md text-base font-medium text-white hover:text-gray-100 hover:bg-gray-700">Acerca de</a>
      <a href="#" class="block px-3 py-2 rounded-md text-base font-medium text-white hover:text-gray-100 hover:bg-gray-700">Servicios</a>
      <a href="#" class="block px-3 py-2 rounded-md text-base font-medium text-white hover:text-gray-100 hover:bg-gray-700">Contacto</a>
    </div>
  </div>
</nav>

</template>


