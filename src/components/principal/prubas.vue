<template>
    <DialogHeader>
      <DialogTitle>Make a Post</DialogTitle>
      <DialogDescription>
        Input the title in the first field and the description in the next one. If you wish to add an image to your post, you can do so as well.
      </DialogDescription>
    </DialogHeader>
    <div class="grid gap-4 py-4">
      <div class="items-center gap-4">
        <Input ref="titleInput" id="title" placeholder="What is happening?" class="col-span-3" />
      </div>
      <div class="grid items-center gap-4">
        <Input ref="descriptionInput" id="description" placeholder="Describe it" class="col-span-3" />
      </div>
      <FileDrop class="flex justify-center h-[25vh] w-[59vh] " :files="files" @upload="startUpload" />
    </div>
    <DialogFooter>
      <Button @click="handleSubmit">Post</Button>
    </DialogFooter>
  </template>
  
  <script setup lang="ts">
  import { ref } from 'vue';
  
  const titleInput = ref<HTMLInputElement | null>(null);
  const descriptionInput = ref<HTMLInputElement | null>(null);
  const files = ref<File[]>([]); // Ref para los archivos
  
  const handleFileUpload = (uploadedFiles: File[]): void => {
    files.value = uploadedFiles; // Actualizar la lista de archivos
    uploadedFiles.map(file => console.log("uploading", file));
  }
  
  const handleSubmit = async (): Promise<void> => {
    const title = titleInput.value?.value;
    const description = descriptionInput.value?.value;
    console.log(title," = ",description)
    console.log("Files:", files.value); // Mostrar los archivos seleccionados
  }
  </script>
  