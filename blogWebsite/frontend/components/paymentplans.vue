<script>
import { ref } from 'vue'
export default {
    props: {
        data: Object
    },
    data() {
        return {
            active: false
        }
    }
}
</script>

<template>
    <section class="md:p-16 relative xl:pt-24 xl:pb-12">
        <div class="container mx-auto">
        <div class="flex flex-col item-center justify-center items-center gap-8 p-10 md:p-0">
            <h1 class="text-lg lg:text-4xl ff-montserrat-bold text-center price-title">{{ data.title }}</h1>
            <div class="flex gap-4 mb-12">
                <button 
                    class="btn-1 text-white ff-montserrat-regular text-sm rounded-3xl">{{ data.btn1 }}</button>
                <button :class="{activebtn:active}" @click="active = !active" class="btn-1 btn-2 text-sm rounded-3xl ff-montserrat-regular">{{ data.btn2 }}</button>
            </div>
        </div>
        <div class="price-cards flex lg:flex-row flex-col items-center justify-center gap-4">
            <div :class="{ highlight: active }" class="w-full xl:w-1/4 card card-plain text-center py-2 relative z-10"
                v-for="item in data.payment">
                <p class="ff-montserrat-bold text-sm pt-4">{{ item.plan }}</p>
                <h1 class="ff-montserrat-regular text-5xl my-8 price">{{ item.price }}</h1>
                <div class="plans py-4 flex justify-center gap-1 border-b">
                    <p class="ff-montseraat-regular text-sm text-black font-bold">{{ item.space }}</p>
                    <p class="ff-montserrat-regular text-sm text">{{ item.spaceText }}</p>
                </div>
                <div class="plans py-4 flex justify-center gap-1 border-b">
                    <p class="ff-montseraat-regular text-sm text-black font-bold">{{ item.bandwidth }}</p>
                    <p class="ff-montserrat-regular text-sm text">{{ item.bandwidthText }}</p>
                </div>
                <div class="plans py-4 flex justify-center gap-1 border-b">
                    <p class="ff-montseraat-regular text-sm text-black font-bold">{{ item.account }}</p>
                    <p class="ff-montserrat-regular text-sm text">{{ item.accountText }}</p>
                </div>
                <div class="plans py-4 flex justify-center gap-1">
                    <p class="ff-montseraat-regular text-sm text-black font-bold">{{ item.subdomain }}</p>
                    <p class="ff-montserrat-regular text-sm text">{{ item.subdomainText }}</p>
                </div>

                <button class="btn-1 text-white ff-montserrat-regular text-sm rounded-3xl mt-5">{{ item.button }}</button>
            </div>
        </div>
    </div>
    </section>
   
</template>

<style lang="css">
.price-title {
    color: #2c2c2c;
}

.text {
    color: #888;
}

.btn-1 {
    padding: 10px 23px;
    background-color: #f96332;
    box-shadow: 0 5px 35px 0 rgba(0, 0, 0, .3);
}
.btn-1:hover{
    background-color: #fa7a50;
    box-shadow: none;
}
.btn-2 {
    background-color: hsla(0,0%,87%,.3);
    color: #444;
    box-shadow: none;
}
.btn-2:hover{
    background-color: #fa7a50;
    color: #ffffff;
}
.card-plain {
    background: transparent;
    box-shadow: none;
    min-height: 450px;
}

.card:first-child>p,
.card:last-child>p {
    color: #9a9a9a;
}

.price::before {
    content: '$';
    position: relative;
    color: #565656;
    top: -17px;
    right: 10px;
    font-size: 26px;
    font-family: 'Montserrat-Bold', sans-serif;
}

.plans {
    max-width: 240px;
    margin: 0 auto;
}

.card:nth-child(2) {
    background: url('../public/images/card2-bg.jpg');
    background-size: cover;
    background-position: 50%;
    background-repeat: no-repeat;
    width: 350px;
    height: 450px;
    border-radius: .1875rem;
}

.card:nth-child(2) p,
.card:nth-child(2) h1 {
    color: white;
}

.card:nth-child(2) {
    box-shadow: 0 20px 50px 0 rgba(0, 0, 0, .3);
}

.card:nth-last-child(2) button {
    background: #ffffff;
    color: #f96332;
}
.card:nth-last-child(2) button:hover{
    background: #fa7a50;
    color: #444;
}
.card:nth-child(2)::after {
    content: '';
    position: absolute;
    z-index: -1;
    width: 350px;
    height: 450px;
    display: block;
    top: 0;
    background-color: rgba(0, 0, 0, .65);
    border-radius: .1875rem;

}

.highlight{
    box-shadow: 0 20px 50px 0 rgba(0, 0, 0, .3);
}

.activebtn{
    background: #ed7e5a;
    color: #ffffff;
}

@media screen and (max-width:1279px) {
     .card:nth-child(2) {
        width: 100%;
    }
    .card:nth-child(2)::after {
        width: 100%;
    }

}
@media screen and (max-width:640px) {
    .btn-1 {
        padding: 10px 20px;
    }
}

@media screen and (max-width:480px) {
    .btn-1 {
        padding: 10px 8px;
    }
}</style>