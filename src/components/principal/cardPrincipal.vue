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
import Carousel from './Carousell.vue'
import { ScrollArea,ScrollBar } from '@/components/ui/scroll-area'
import {
  Tabs,
  TabsContent,
  TabsList,
  TabsTrigger,
} from '@/components/ui/tabs'
</script>

<template>

  <Card :class="cn(' ml-4 w-[940px] h-[600px]', $attrs.class ?? '')">
    <Tabs default-value="account"  class="w-[400px]">
    <CardHeader>
        <CardTitle>Home</CardTitle>
        <CardDescription>here you can share an see others images</CardDescription>
      </CardHeader>
      <div class="m-4 space-between flex items-center">
        <TabsList >
          <TabsTrigger value="account">
            Feed
          </TabsTrigger>
          <TabsTrigger value="password" >
            For you
          </TabsTrigger>
        </TabsList>
        <div class=" ml-96">
            <Button>
            <PlusCircleIcon class="mr-2 h-4 w-4" />
            Add music
            </Button>
        </div>
        </div>
      <TabsContent value="account">
      <div class="flex justify-center  h-screen">
        <ScrollArea class="h-72 w-48 rounded-md">

        <div class="grid place-items-center">
          <CardContent class="grid gap-4">
            <Carousel/>
          </CardContent>
        </div>

        <div class="grid place-items-center">
          <CardContent class="grid gap-4">
            <Carousel/>
          </CardContent>
        </div>

        </ScrollArea>
      </div>
      </TabsContent>
      <TabsContent value="password">
        <div class="flex justify-center  h-screen">
        <ScrollArea class="h-72 w-48 rounded-md">

        <div class="grid place-items-center">
          <CardContent class="grid gap-4">
            <Carousel/>
          </CardContent>
        </div>

        <div class="grid place-items-center">
          <CardContent class="grid gap-4">
            <Carousel/>
          </CardContent>
        </div>

        </ScrollArea>
        </div>
      </TabsContent>
   

    <CardFooter>
       
      </CardFooter>

    </Tabs>
  </Card>


</template>