<script setup lang="ts">
import { useHead } from '@vueuse/head'
import { createClient, provideClient } from '@urql/vue'

const client = createClient({
  url: 'http://localhost:4000/graphql'
})

provideClient(client)


// https://github.com/vueuse/head
// you can use this to manipulate the document head in any components,
// they will be rendered correctly in the html results with vite-ssg
useHead({
  title: 'Plant',
  meta: [
    { name: 'description', content: 'Opinionated Vite Starter Template' },
  ],
})
</script>

<template>
  <router-view />
</template>
