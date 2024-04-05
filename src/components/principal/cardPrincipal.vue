<script setup lang="ts">
import { Button } from '@/components/ui/button'
import {
  Card,
  CardContent,
  CardDescription,
  CardFooter,
  CardHeader,
  CardTitle,
} from '@/components/ui/card'
import { PlusCircleIcon } from 'lucide-vue-next'
import { Switch } from '@/components/ui/switch'
import { cn } from '@/lib/utils'
import CarouselMod from './CarouselMod.vue'
import { ScrollArea,ScrollBar } from '@/components/ui/scroll-area'
import {
  Dialog,
  DialogContent,
  DialogDescription,
  DialogFooter,
  DialogHeader,
  DialogTitle,
  DialogTrigger,
} from '@/components/ui/dialog'
import {
  Tabs,
  TabsContent,
  TabsList,
  TabsTrigger,
} from '@/components/ui/tabs'
import AddPosts from './addPosts.vue'


</script>
<template>

<Card :class="cn(' ml-4 w-full sm:w-[90%] md:w-[90%] lg:w-[70%] xl:w-[68%] h-[87vh]', $attrs.class ?? '')">

 
    <CardHeader>
        <CardTitle>Home</CardTitle>
        <CardDescription>here you can share an see others images</CardDescription>
      </CardHeader>
      <Tabs class="m-4 flex flex-col items-center" default-value="feed">
        <div class="w-full sm:w-auto mb-10 flex justify-between items-center">
          <TabsList>
            <TabsTrigger value="account">
              Feed
            </TabsTrigger>
            <TabsTrigger value="password">
              For you
            </TabsTrigger>
          </TabsList>
          <div class="ml-12">
            <Dialog>
            <DialogTrigger as-child>
              <Button>
              <PlusCircleIcon class="mr-2 h-4 w-4" />
                Add Posts
              </Button>
            </DialogTrigger>
            <DialogContent class="sm:max-w-[425px]">
              <AddPosts/>
            </DialogContent>
            </Dialog>
          </div>
        </div>

        <div class="flex justify-center h-screen">
          <ScrollArea class="h-72 w-48vh rounded-md">
            <div class="grid place-items-center">
              <CardContent class="grid gap-4">
                <CarouselMod/>
              </CardContent>
            </div>

            <div class="grid place-items-center">
              <CardContent class="grid gap-4">
                <CarouselMod/>
              </CardContent>
            </div>
          </ScrollArea>
        </div>
      </Tabs>

    <CardFooter>
       
      </CardFooter>

  
  </Card>


</template>

