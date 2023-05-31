<template>
    <div :class="[getShowHeader]" class="w-full fixed z-50 py-4">
        <header>
            <div class="container mx-auto">
                <nav>
                <div class=" flex flex-wrap items-center" id="links-wrapper">
                    <tez-link to="/discover-india" title="Discover India"
                        class="flex items-center ff-montserrat-regular text-sm lg:text-xl text-white flex-grow logo">{{ data.logo
                        }}</tez-link>
                    <input id="toggle" data-collapse-toggle="navbar-default" type="checkbox"
                        class="group inline-flex items-center p-2 ml-3 text-sm text-gray-500 lg:hidden hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-gray-200 toggle-menu invisible"
                        aria-controls="navbar-default" aria-expanded="false">
                    <label for="toggle" class="inline-flex lg:hidden" id="btn-nav">
                        <svg class="w-6 h-6" xmlns="http://www.w3.org/2000/svg" x="0px" y="0px" width="50" height="50" viewBox="0,0,256,256"
                            style="fill:#000000;">
                            <g fill="#f96332" fill-rule="nonzero" stroke="none" stroke-width="1" stroke-linecap="butt"
                                stroke-linejoin="miter" stroke-miterlimit="10" stroke-dasharray="" stroke-dashoffset="0"
                                font-family="none" font-weight="none" font-size="none" text-anchor="none"
                                style="mix-blend-mode: normal">
                                <g transform="scale(5.12,5.12)">
                                    <path d="M0,7.5v5h50v-5zM0,22.5v5h50v-5zM0,37.5v5h50v-5z"></path>
                                </g>
                            </g>
                        </svg>
                    </label>

                    <div class="hidden w-full lg:block lg:w-auto nav-links bg-black lg:bg-transparent" id="navbar-default">
                        <ul
                            class="nav-wrapper flex flex-col lg:items-center items-start lg:flex-row lg:space-x-8 lg:mt-0 lg:text-sm lg:font-medium lg:border-0">
                            <li class="!ml-0 nav-item py-4 px-1 lg:px-4" v-for="item in data.links">
                                <tez-link :to="item.links" :title="item.links"
                                    class="block lg:inline-block my-1 text-sm leading-5 text-white ff-montserrat-regular transition-colors duration-200 transform lg:my-0 no-underline uppercase rounded">{{
                                        item.links }}</tez-link>
                            </li>
                        </ul>
                    </div>
                </div>
            </nav>
            </div>
        </header>
    </div>
</template>
<script>
export default {
    props: {
        data: Object
    },
    data() {
        return {
            showHeader: true,
            windowWidth: null,
            lastScrollPosition: 0,


        }
    },
    methods: {
        onScroll() {
            if (window.pageYOffset > 0) {
                if (this.showHeader) this.showHeader = false;
                return;
            } else {
                if (!this.showHeader) this.showHeader = true;
            }
        },
    },
    computed: {
        getShowHeader() {
            return !this.showHeader ? "stickyScrolled" : "";
        },
        // getIsServices() {
        //     return this.bgHeaderWhite
        //         ? "bg-white dark:bg-themedark-10 headerHover"
        //         : "";
        // },
    },
    mounted() {
        this.lastScrollPosition = window.pageYOffset;
        window.addEventListener("scroll", this.onScroll);
    },
}
</script>
<style lang="scss">
.stickyScrolled {
    background-color: black;
    top: 0;
}

@media screen and (min-width:1024px) {
    .nav-wrapper li:last-child{
    padding: 0;
}
}
.nav-item:last-child a {
    background: #F96332;
    padding: 14px 20px;
    text-transform: capitalize;
}

.nav-item:last-child a:hover {
    background: #f18967;
    color: black;
}

.nav-item:first-child a::before {
    content: ' ';
    background: url('../public/images/box.svg');
    background-size: 20px;
    background-position: center;
    vertical-align: bottom;
    display: inline-block;
    width: 20px;
    height: 20px;
    margin-right: 5px;
}

.nav-item:first-child a:hover::before {
    background: url('../public/images/box-h.svg');
    background-size: 20px;
}

.nav-item:nth-child(2) a::before {
    content: ' ';
    background: url('../public/images/section.png');
    background-size: 20px;
    background-position: center;
    vertical-align: bottom;
    display: inline-block;
    width: 20px;
    height: 20px;
    margin-right: 5px;
}

.nav-item:nth-child(2) a:hover::before {
    background: url('../public/images/section-h.png');
    background-size: 20px;
}

.nav-item:nth-child(3) a::before {
    content: ' ';
    background: url('../public/images/example.svg');
    background-size: 20px;
    background-position: center;
    vertical-align: bottom;
    display: inline-block;
    width: 20px;
    height: 20px;
    margin-right: 5px;
}

.nav-item:nth-child(3) a:hover::before {
    background: url('../public/images/img-h.svg');
    background-size: 20px;
}

.nav-item:first-child a:hover,
.nav-item:nth-child(2) a:hover,
.nav-item:nth-child(3) a:hover,
.logo:hover {
    color: #f18967;
}

@font-face {
    font-family: 'Montserrat-Regular';
    src: url('../public/fonts/Montserrat-Regular.woff') format('woff'),
        url('../public/fonts/Montserrat-Regular.woff2') format('woff2');
}

@font-face {
    font-family: 'Montserrat-Bold';
    src: url('../public/fonts/Montserrat-Bold.woff') format('woff'),
        url('../public/fonts/Monteserrat-Bold.woff2') format('woff2');
}

.ff-montserrat-regular {
    font-family: 'Montserrat-Regular', sans-serif;
}

.ff-montserrat-bold {
    font-family: 'Montserrat-Bold', sans-serif;
}

.toggle-menu:checked~div {
    display: block !important;
}


</style>
