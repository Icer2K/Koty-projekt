<template>
    <div id="header">
        <header class="header" >
            <div class="navbar">
                <div class="logo d-flex">
                    <img alt="Vue logo" class="logo" src="../assets/logoCats.png" width="70" height="70" />
                    <h1 class="font-light gluten m-0 head1 align-middle">
                        YourCats
                    </h1>
                </div>
                
                <nav class="d-flex flex-fill justify-content-around">
                    <div class="p-2 bg-primary-light rounded-pill">
                        <a href="" class="font-light">Home</a>
                    </div>
                    <div class="p-2 bg-primary-light rounded-pill">
                        <a href="" class="font-light">About</a>
                    </div>
                    <div class="p-2 bg-primary-light rounded-pill">
                        <a href="" class="font-light">Service</a>
                    </div>
                    <div class="p-2 bg-primary-light rounded-pill">
                        <a href="#cats" class="font-light">Blog</a>
                    </div>
                    <div class="p-2 bg-primary-light rounded-pill">
                        <a href="#contact" class="font-light">Contacts</a>
                    </div>
                </nav>
            </div>
        </header>
        <img alt="Vue logo" class="logo" src="../assets/header.svg" width="100%" height="20px" />
    </div>
</template>

<script>

export default {
    name: "headerCats",
    props: {
        // msg:String,
    },
    data(){
        return {

        }
    },
    methods: {
        
    },
    created() {
        
    },
}
</script>