<script>
import { ref } from 'vue'
import hello from '../components/hello.vue'
export default {
  props: {
    data: Object
  },
 mounted(){
  localStorage.title = this.data.title;
}
}
</script>
<template>
  <section class="p-5 md:p-5 relative xl:pt-24 xl:pb-12">
    <div class="container mx-auto p-5 lg:p-0 flex flex-col item-center justify-center items-center gap-8">
      <h1 class="text-lg lg:text-3xl ff-montserrat-bold text-center sm:w-full" v-once>{{ data.title }}</h1>
      <h3 class="text-sm lg:text-xl text-gray-300 ff-montserrat-regular text-center xl:w-2/4 mx-auto pb-5 sm:w-full">{{ data.description }}
      </h3>
    </div>
  </section>
</template>
<style lang="css">
.title {
  color: #2C2C2C;
}

.desc {
  color: #AAB2B4;
}
</style>
