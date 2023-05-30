<script setup lang="ts">
defineProps<{ authors: any }>();
</script>
<template>
    <div
        class="w-full shadow-lg hover:shadow-2xl transition-all delay-100 ease-in rounded-md px-3 h-full mt-14 hover:cursor-pointer border border-gray-800">
        <div class="card px-5 py-6 flex flex-wrap h-full flex-col justify-center items-center gap-3">
            <tez-link :to="authors.slug" class="flex items-center text-black no-underline">
                <img class="rounded-full" v-tez-src="authors.picture.url" :alt="authors.picture.alternativeText"
                    height="50" width="50" />
            </tez-link>
            <h1 class="text-indigo-900 font-sans font-bold text-xl">{{ authors.name }}</h1>
            <h3 class="text-gray-900 font-sans text-lg font-semibold">{{ authors.info }}</h3>
        </div>
    </div>
</template>
<style lang="css">
div.tezIterator > div{
  width: 100%;
  padding: 0px 14px;
  margin-bottom: 20px;
}
@media (min-width:1024px) {
  div.tezIterator > div{
    width: 50%;
    padding: 0px 14px;
    margin-bottom: 30px;
  }
}
@media (min-width:1280px) {
  div.tezIterator > div{
    width: 33.33%;
    padding: 0px 14px;
    margin-bottom: 40px;

  }
}
</style>