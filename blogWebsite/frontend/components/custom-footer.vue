<script setup lang="ts">
import { ref } from 'vue'
defineProps<{ data: any }>()

</script>

<template>
    <footer class="footer overflow-hidden py-3">
        <div class="container mx-auto">
            <div class="flex flex-wrap -mx-4 items-center justify-between">
                <div class="w-full xl:w-3/6 px-4 text-center xl:text-left">
                    <ul
                        class="footer-links flex flex-col items-center justify-center xl:justify-start lg:flex-row md:space-x-8 md:mt-0 md:text-sm md:font-medium md:border-0">
                        <li class="!ml-0 p-4" v-for="item in data.footer">
                            <tez-link :to="item.links" :title="item.links"
                                class="footer-links block md:inline-block my-1 text-sm leading-5 text-black ff-montserrat-regular transition-colors duration-200 transform md:my-0 no-underline uppercase rounded">{{
                                    item.links }}</tez-link>
                        </li>
                    </ul>
                </div>
                <div class="copyright w-full lg:w-3/5 xl:w-6/12 my-4 lg:my-0 px-4 text-center mx-auto mt-4">
                    <p class="p-0 my-0 text-center xl:text-right text-base ff-montserrat-regular text-black">
                        {{ data.copyright }}
                    </p>
                </div>
            </div>
        </div>
    </footer>
</template>

<style lang="css">
.footer {
    background: #f2f2f2;
}

.footer-links:hover {
    color: #fa7a50;
}
.copyright p::before{
    content: '©';
}
@media screen and (min-width:1024px) {
    .footer-links li:first-child{
    padding: 0;
}
}
</style>