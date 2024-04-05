<template>
    <Carousel class="relative w-full max-w-xs">
      <CarouselContent>
        <template v-for="(product, index) in products" :key="index">
          <CarouselItem>
            <div class="p-2 ml-auto mr-auto w-auto h-auto">
              <img :src="getImageUrl(product.images)" alt="verd" width="1366" height="190" />
            </div>
          </CarouselItem>
        </template>
      </CarouselContent>
      <CarouselPrevious />
      <CarouselNext />
    </Carousel>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  import { Carousel, CarouselContent, CarouselItem, CarouselNext, CarouselPrevious } from '@/components/ui/carousel';
  import { Card, CardContent } from '@/components/ui/card';
  
  const products = ref([]);
  
  const fetchData = async () => {
    try {
      const response = await fetch('https://api-uptc-store.vercel.app/products');
      const data = await response.json();
      console.log('Datos recibidos:', data);
      products.value = data.products;
    } catch (error) {
      console.error('Error fetching data:', error);
    }
  };
  
  fetchData();
  
  const getImageUrl = (images) => {
    return images ? images.secure_url : '';
  };
  </script>
  