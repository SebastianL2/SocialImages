<script setup lang="ts">
import { BellRing, Check } from 'lucide-vue-next'

import { Button } from '@/components/ui/button'
import {
  Card,
  CardContent,
  CardDescription,
  CardFooter,
  CardHeader,
  CardTitle,
} from '@/components/ui/card'
import { Switch } from '@/components/ui/switch'
import { cn } from '@/lib/utils'
import Carousel from './carousell.vue'

const notifications = [
  {
    title: 'Your call has been confirmed.',
    description: '1 hour ago',
  },
  {
    title: 'You have a new message!',
    description: '1 hour ago',
  },
  {
    title: 'Your subscription is expiring soon!',
    description: '2 hours ago',
  },
]
</script>

<template>
  <Card :class="cn(' ml-4 w-[940px] h-[600px]', $attrs.class ?? '')">
    <CardHeader>
      <CardTitle>Your Posts</CardTitle>
      <CardDescription>You have 3 unread messages.</CardDescription>
    </CardHeader>
    <div class="grid place-items-center">
    <CardContent class="grid gap-4">
        <Carousel/>
    </CardContent>
    </div>
    <CardFooter>

    </CardFooter>
  </Card>
</template>