<script>
import { ref } from 'vue'
export default {
    props: {
        data: Object
    },
    data() {
        return {
            name: '',
            email: '',
            msg: '',
        }
    },
    mounted() {
        if (localStorage.name) {
            this.name = localStorage.name;
        }
        if (localStorage.email) {
            this.email = localStorage.email;
        }
        if (localStorage.msg) {
            this.msg = localStorage.msg;
        }
    },
    methods: {
        persist() {

            if(this.name === '' || this.email === '' || this.msg === ''){
                window.alert('Please submit all the details!!!')
            }

            localStorage.name = this.name;
            localStorage.email = this.email;
            localStorage.msg = this.msg;
        },
        reset(){
            localStorage.removeItem('name');
            this.name=''
            localStorage.removeItem('email');
            this.email=''
            localStorage.removeItem('msg');
            this.msg=''
        }
    }
}
</script>
<template>
    <section class="p-5 sm:p-10 md:p-16 relative xl:pt-24 xl:pb-12">
        <div class="container mx-auto">
        <div class="flex flex-col item-center justify-center items-center gap-6 p-5 md:p-0">
            <h1 class="text-lg lg:text-3xl ff-montserrat-bold text-center title">{{ data.heading }}</h1>
            <h3 class="text-sm text-gray-300 ff-montserrat-regular text-center mx-auto pb-5 desc">{{ data.title }}
            </h3>
        </div>

        <div class="flex flex-col justify-center space-y-6 items-center pt-3 pb-7">
            <div class="relative w-full xl:w-4/12">
                <div class="absolute inset-y-0 left-0 flex items-center pl-4 pointer-events-none">
                <img src="../public/images/user-icn.png" alt="user" width="16" height="16">
            </div>
            <input type="text" id="text" name="text" placeholder="First Name..."
                class="py-4 px-10 w-full appearance-none rounded-full border border-gray-300 ff-montserrat-regular text-sm"
                v-model="name" />
            </div>

            <div class="relative w-full xl:w-4/12">
                <div class="absolute inset-y-0 left-0 flex items-center pl-4 pointer-events-none">
                <img src="../public/images/mail-icn.png" alt="user" width="16" height="16">
            </div>
            <input type="email" id="mail" name="mail" placeholder="Email Here..."
                class="w-full py-4 px-10 appearance-none rounded-full border border-gray-300 ff-montserrat-regular text-sm"
                v-model="email" />
            </div>

            <textarea name="message" id="" cols="80" rows="4" placeholder="Type a message..."
                class="w-full xl:w-4/12 ff-montserrat-regular text-sm mt-5" v-model="msg"></textarea>

            <button @click="persist" id="btn" class="w-full xl:w-4/12 rounded-full p-4 text-white ff-montserrat-regular text-sm"><span
                    id="showHide">Send</span> Message</button>

            <button @click="reset" class="hidden">Reset</button>
        </div>
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


textarea {
    max-width: 100%;
    max-height: 80px;
    padding: 10px 10px 0 0;
    resize: none;
    border: none;
    border-bottom: 1px solid #e3e3e3;
    border-radius: 0;
    line-height: 2;
}

#btn {
    background-color: #f96332;
}
#btn:hover{
    background-color: #fa7a50;
    color: #fff;
    box-shadow: none;
}
input:focus{
    outline: 1px solid #fa7a50;
}
textarea:focus{
    outline: none;
}
textarea:focus{
    border-bottom: 1px solid #fa7a50;
    transition: 0.8s;
}

</style>
