<script setup lang="ts">
import { ref } from 'vue'
defineProps<{ data: any }>()

</script>

<template>
    <section class="lg:p-20 w-full bg-cover bg-center bg-no-repeat flex flex-col relative section-img" v-bind:style="[
        data.image.url
            ? { backgroundImage: 'url(' + data.image.url + ')' }
            : '',
    ]">
        <div class="pt-8 relative z-10">
            <h1 class="text-sm lg:text-4xl text-center text-white ff-montserrat-bold pb-6">{{ data.title }}</h1>
            <p class="text-sm lg:text-2xl text-white text-center w-4/5 xl:w-2/6 mx-auto pb-5 font-light">{{ data.description }}</p>
        </div>

        <div class="container mx-auto relative z-10">
            <div class="flex lg:flex-row flex-col justify-center gap-8 py-10">
                <div class="pt-20 pb-10 cards sm:w-full xl:w-3/12 bg-white shadow-lg hover:shadow-2xl transition-all delay-100 ease-in rounded-md px-3 mt-14 hover:cursor-pointer border relative"
                    v-for="item in data.cards">
                    <h3 class="text-sm lg:text-base text-center ff-montserrat-regular w-full xl:w-4/5 mx-auto description pb-10 pt-6">{{ item.title }}</h3>
                    <p class="text-sm lg:text-2xl pt-10 pb-3 text-center ff-montserrat-regular text-black">{{ item.user }}</p>
                    <p class="text-sm lg:text-xl text-center ff-montserrat-bold text-gray-400">{{ item.usertag }}</p>
                </div>
            </div>
        </div>
    </section>
</template>

<style lang="css">


.description{
    color: #AAB2B4;
}
.cards::after{
    content: '';
    background: url('../public/images/quote.svg');
    display: inline-block;
    background-position: center;
    vertical-align: middle;
    background-repeat: no-repeat;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, 0px);
    background-size: contain;
    width: 32px;
    height: 32px;
    padding-top: 70px;
}
.cards:first-child h3::before{
    content: '';
    background: url('../public/images/card-1.jpg');
    width: 100px;
    height: 100px;
    border-radius: 50%;
    display: inline-block;
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
    position: absolute;
    top: 180px;
    left: 50%;
    transform: translate(-50%,-234px);
    box-shadow: 0 10px 25px 0 rgba(0,0,0,.3);
}
.cards:nth-child(2) h3::before{
    content: '';
    background: url('../public/images/card-2.jpg');
    width: 100px;
    height: 100px;
    border-radius: 50%;
    display: inline-block;
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
    position: absolute;
    top: 180px;
    left: 50%;
    transform: translate(-50%,-234px);
    box-shadow: 0 10px 25px 0 rgba(0,0,0,.3);
}
.cards:last-child h3::before{
    content: '';
    background: url('../public/images/card-3.jpg');
    width: 100px;
    height: 100px;
    border-radius: 50%;
    display: inline-block;
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
    position: absolute;
    top: 180px;
    left: 50%;
    transform: translate(-50%,-234px);
    box-shadow: 0 10px 25px 0 rgba(0,0,0,.3);
}
.section-img::after{
    position: absolute;
    z-index: 1;
    width: 100%;
    height: 100%;
    display: block;
    left: 0;
    top: 0;
    content: "";
    background-color: rgba(0,0,0,.7);
}
</style>