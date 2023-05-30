<script setup lang="ts">
import { ref } from 'vue'
import AuthorCard from "./author-details.vue"
defineProps<{ data: any }>()

</script>
<template>
<div class="container mx-auto p-5 sm:p-10 md:p-16 relative">
    <div class="flex justify-center items-center min-h-screen">
    <TezLazy class="tezLazy" :sourcePath="data.dynamicSourcePath" v-slot="source">
      <tez-iterator class="tezIterator flex flex-wrap -mx-4" :items="source.items" v-slot="authors">
        <AuthorCard :authors="authors"/>
      </tez-iterator>
    </TezLazy> 
    </div>
</div>
</template>