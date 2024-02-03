<script setup lang="ts">
import { Button } from '@/components/ui/button'
import {
  Calculator,
  Calendar,
  Cloud,
  CreditCard,
  Github,
  Linkedin,
  Settings,
  Smile,
  User,
} from 'lucide-vue-next'
import { onMounted, ref, watch } from 'vue'
import { SearchIcon } from 'lucide-vue-next'
import CommandMenu from './ComandMenu.vue'
import Table from './Table.vue'
</script>
<template>
 <div className="relative">
    <div className="fixed w-full top-0 z-50 backdrop-blur-md ">
      <header className="p-1 border-b bg-opacity-80">
        <div className="container mx-auto flex justify-between items-center">
          <div className="text-ms flex font-bold">SebasCloud <Cloud/></div>
          <nav className="flex   items-center space-x-4">
          <CommandMenu/>
            <Button  variant="ghost" size="icon" asChild>
            <Link href="https://github.com/SebastianL2"><Github/></Link>
            </Button>
            <Button  variant="ghost" size="icon" asChild>
            <Link href="https://www.linkedin.com/in/sebastian-cely-a92242203/"><Linkedin/></Link>
            </Button>
       
             
          </nav>
        </div>
      </header>
    </div>
    <div className="h-16"></div>
    </div>
<div>
<Table>

</Table>

</div>
</template>