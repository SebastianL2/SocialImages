<script setup lang="ts">
import { Button } from '@/components/ui/button'
import {
  Dialog,
  DialogContent,
  DialogDescription,
  DialogFooter,
  DialogHeader,
  DialogTitle,
  DialogTrigger,
} from '@/components/ui/dialog'
import { Input } from '@/components/ui/input'
import { Label } from '@/components/ui/label'
import { ref } from 'vue';
const titleInput = ref<HTMLInputElement | null>(null);
const descriptionInput = ref<HTMLInputElement | null>(null);

import {defineAsyncComponent} from "vue"

let uploadedFiles: File[] = [];
const FileDrop = defineAsyncComponent(()=>import(/*webpackChunkName:"filedrop"*/ "./FileDrop.vue"))
function startUpload(files : File[]) : void
{
   
    files.map(file =>  uploadedFiles.push(file))
    
}


const handleSubmit = async (): Promise<void> => {

  const title = titleInput.value?.value;
  const description = descriptionInput.value?.value;

  console.log(title, " = ", description);
  if (uploadedFiles.length > 0) {
    const selectedFile = uploadedFiles[0]; // Suponiendo que solo se carga un archivo
    
    const url = `https://api.cloudinary.com/v1_1/ddsuzqzgh/image/upload`;
    
    try {
      const formData = new FormData();
      formData.append("file", selectedFile);
      formData.append('upload_preset', 'v8xxvhbs');
      
      const response = await fetch(url, {
        method: 'POST',
        body: formData
      });
      
      if (response.ok) {
        const data = await response.json();
        console.log('Datos de la imagen: ', data);
        const postData = {
          name: title, // Usar 'name' en lugar de 'title'
          description: description,
          price: 0, 
          secure_url: data.secure_url,
          public_id: data.public_id,
          stock: 0, 
          availability: true, 
          category: '651a01d23f0e950ef7991a19', 
          subcategory: '' 
        };

        const postResponse = await fetch('https://api-uptc-store.vercel.app/products/', {
          method: 'POST',
          body: JSON.stringify(postData),
          headers: {
            'Content-Type': 'application/json'
          },
          
        });

        if (postResponse.ok) {
          console.log('Datos enviados correctamente a la API.');
        } else {
          console.error('Error al enviar datos a la API.');
        }

      } else {
        console.error('Error al subir la imagen a Cloudinary.');
      }
    } catch (error) {
      console.error('Error en la solicitud a Cloudinary:', error);
    }
  } else {
    console.warn('No se ha seleccionado ningún archivo.');
  }

}
</script>

<template>
      <DialogHeader>
        <DialogTitle>Make a Post</DialogTitle>
        <DialogDescription>
          Input the title in the first field and the description in the next one. If you wish to add an image to your post, you can do so as well.
        </DialogDescription>
      </DialogHeader>
      <div class="grid gap-4 py-4">
        <div class="items-center gap-4">
        
          <input ref="titleInput" id="name" placeholder="What is hapening?" class="col-span-3" />
        </div>
        <div class="grid  items-center gap-4">

          <input ref="descriptionInput" id="username"  placeholder="Describe it" class="col-span-3" />
        </div>
        
       
        <FileDrop class="flex justify-center h-[25vh] w-[59vh] " @upload="startUpload" />
     
   
      </div>
      <DialogFooter>
        <Button @click="handleSubmit" type="submit">
          Post
        </Button>
      </DialogFooter>

</template>

<style lang="scss" scoped>

</style>