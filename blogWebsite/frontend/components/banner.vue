<script setup lang="ts">
import { ref } from 'vue'
defineProps<{ data: any }>()

</script>

<template>
        <div class="banner before:absolute before:z-0 before:w-full before:h-full before:block before:top-0 before:left-0 before:content-[''] before:bg-[#0000004d] h-screen sm:h-[50vh] lg:h-[58vh] w-full bg-cover bg-center bg-no-repeat flex flex-col justify-center items-center relative" v-bind:style="[
            data.img.url
              ? { backgroundImage: 'url(' + data.img.url + ')'}
              : '',
          ]">
            <div class="relative z-10">
                <h1 class="text-lg md:text-3xl lg:text-5xl text-center text-white ff-montserrat-bold">{{ data.text }}</h1>
            </div>
            <div class="flex gap-3 relative z-10">
                <div class="justify-center items-center mt-8" v-for="item in data.iconsList">
                    <tez-link :to="item.hash" class="flex items-center text-black no-underline">
                        <img class="icons rounded-full hover:cursor-pointer" v-tez-src="item.icons.url" :width="40" :height="40" />
                    </tez-link>
                </div>
            </div>
        </div>
        
</template>

<style lang="css">
.icons:hover{
    transform: rotateY(360deg);
    transition: 1.5s;
}

@media screen and (max-width: 640px) {
    .banner{
        height: 50vh;
    }
}
</style>    