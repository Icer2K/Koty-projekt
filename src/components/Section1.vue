<template>
    <section class="container-fluid section" id="cats">
        cokolwiek1
        <div class="row">
            <div class="col-3" v-for="(cat, index) in result" :key="index.id">
                <!-- {{index}} -->
                <div>Nazwa: {{result[index].image}}</div>
                {{image}}
                <!-- <div>Nazwa: {{cat.name}}</div>
                <div>Nazwa: {{cat.wikipedia_url}}</div>
                <div>Obraz: {{cat.image}}</div> -->
                <!-- <div>Obraz: {{cat.image}} {{obrazUrl(cat.image).url}}</div> -->
                <!-- <img :src="cat.image.url" alt=""> -->
            </div>
        </div>
    </section>
</template>

<script>
import axios from "axios";
import lodash from "lodash";

export default {
    name: "section1",
    props: {
        // msg:String,
        image: Object,
    },
    data(){
        return {
            URL: "https://api.thecatapi.com/v1/",
            apiKey: '4d3e0448-10d7-419b-a33d-f84ecbb0caf4',
            result: [],
            urls:[],
            tablica:[]
        }
    },
    methods: {
        obrazUrl(image){
            console.log(image, "image");
            return image;
        },

        getUrls(){
            const arr = this.result[0];
            // console.log(typeof arr, "arr");
            // for (let index = 0; index < arr.length; index++) {
            //     const element = arr[index].image.url;
            //     this.tablica.push(element);
            //     console.log(element);
            // }
            //     console.log(this.tablica, "jjj");
            // const jjj = lodash.dropRightWhile(this.result.image, 'url')
        },

        async getCats(){
        const config = {
            method: 'get',
            url: `${this.URL}breeds/list`,
            // url: 'https://api.thecatapi.com/v1/breeds/search?li',
            headers: { 
            'Content-Type': 'application/json', 
            'x-api-key': `${this.apiKey}`
            }
        };
        await axios(config)
            .then(res => {
                if (res.status == 200) {
                    this.result = res.data;
                    console(this.result, "refffs");
                } else {
                    console.log(res.statusText);
                }
            })
            .catch(err => {
                console.log(err);
            })
        }
    },
    mouted(){
        // this.getUrls();
    },

    created() {
        // this.getCats();
        // setTimeout(() => {
            
        //     this.getUrls();
        // }, 1500);
    },
}
</script>