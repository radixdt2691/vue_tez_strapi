<script setup lang="ts">
import { ref } from 'vue'
defineProps<{ data: any }>()

</script>
<template>
    <div class="container mx-auto p-5 sm:p-10 md:p-16 relative xl:pt-10 xl:pb-12 pb-20">
        <div class="image pb-4 xl:pb-0 ">
            <img class="mx-auto sm:ml-0 xl:ml-44 rounded h-full" v-tez-src="data.image.url" :width="641" :height="335"
            :alt="data.image.alternativeText">
        </div>
        <img class="mx-auto rounded xl:absolute xl:top-28 xl:right-72" v-tez-src="data.image_Two.url" :width="546" :height="341"
            :alt="data.image_Two.alternativeText">

        <div class="flex flex-col xl:flex-row gap-8">
            <div class="flex flex-col gap-16">
                <div class="quote-wrapper w-full xl:w-56">
                    <p class="para ff-montserrat-regular pb-5 pt-5">"Over the span of the satellite record, Arctic sea ice
                        has been declining significantly,
                        while sea ice in the Antarctica increased very slightly"</p>
                    <p class="para ff-montserrat-regular pb-5">-NOAA</p>
                </div>
                <div class="mx-auto">
                    <img src="../public/images/business.png" alt="business" width="650" height="340" class="rounded">
                </div>
            </div>
            <div class="long-description w-full xl:w-2/4 pt-3 xl:pt-40">
                <h3 class="ff-montserrat-regular text-black text-xl lg:text-2xl title w-full xl:w-2/4 pb-5">
                    So What does the new record for the lowest level of winter ice actually mean
                </h3>
                <p class="desc xl:w-3/5 ff-montserrat-regular pb-5">The Arctic Ocean freezes every winter and much of
                    the sea-ice then thaws every summer, and that
                    process will continue whatever happens with climate
                    change. Even if the Arctic continues to be one of the
                    fastest-warming regions of the world, it will always be
                    plunged into bitterly cold polar dark every winter. And
                    year-by-year, for all kinds of natural reasons, there's
                    huge variety of the state of the ice.</p>

                <p class="desc xl:w-3/5 ff-montserrat-regular pb-5">
                    For a start, it does not automatically follow that a
                    record amount of ice will melt this summer. More
                    important for determining the size of the annual
                    thaw is the state of the weather as the midnight sun
                    approaches and temperatures rise. But over the more
                    than 30 years of satellite records, scientists have
                    observed a clear pattern of decline, decade-by-
                    decade.
                </p>

                <p class="desc xl:w-3/5 ff-montserrat-regular pb-5">
                    The Arctic Ocean freezes every winter and much of
                    the sea-ice then thaws every summer, and that
                    process will continue whatever happens with climate
                    change. Even if the Arctic continues to be one of the
                    fastest-warming regions of the world, it will always be
                    plunged into bitterly cold polar dark every winter. And
                    year-by-year, for all Kinds of natural reasons, there's
                    huge variety of the state of the ice.
                </p>
            </div>

        </div>
    </div>
</template>

<style>
.quote-wrapper {
    border: 1px solid #F96332;
    padding: 5px 20px;
    margin-left: 430px;
    margin-top: 61px;
}

.para {
    color: #faada9;
    line-height: 1.8;
}

.desc {
    color: #AAB2B4;
}
.image{
    height: 335px;
}
img{
    box-shadow: 0 10px 25px 0 rgba(0,0,0,.3);
}
@media screen and (max-width: 640px){
    .image{
        height: unset;
    }
}
@media screen and (max-width: 1280px) {
    .quote-wrapper{
        margin-left: 0px;
    }
}
</style>