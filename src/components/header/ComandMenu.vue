<script lang="ts" setup>

import { onMounted, ref, watch } from 'vue'
import { Button } from '@/components/ui/button'
import {
  CommandDialog,
  CommandEmpty,
  CommandGroup,
  CommandInput,
  CommandItem,
  CommandList,
  CommandSeparator,
} from "@/components/ui/command"


const isOpen = ref(false)


</script>
<template>
       <Button
            variant="outline"
            class="w-72 h-8 px-3 hidden lg:flex lg:justify-between lg:items-center"
            @click="isOpen = true"
        
          >
            <div class="flex items-center">
              <SearchIcon class="w-4 h-4 mr-2 text-muted-foreground" />
              <span class="text-muted-foreground"> Search for anything... </span>
            </div>
            <div class="flex items-center gap-x-1">
              <Kbd> <span>⌘</span>K </Kbd>
            </div>
          </Button>
</template>