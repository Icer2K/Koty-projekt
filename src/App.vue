<script setup>
// import HelloWorld from './components/HelloWorld.vue'
// import TheWelcome from './components/TheWelcome.vue'
</script>

<template>
    <div>
        <Header />
        <!-- <header>
          <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

          <div class="wrapper">
            <HelloWorld msg="You did it!" />
          </div>
        </header> -->

        <main class="mb-5">          
            <!-- <section class="container-fluid section"><TheWelcome /></section> -->
            <!-- <Section1 :image="image"/> -->
            <section class="container-fluid p-0 pt-5 section section3 mb-5">
              <div id="search">
                <div class="container ">
                  <div class="d-flex flex-column justify-content-center align-items-center mySearch">
                    <h1 class="favoriteCat gluten">Search for your favorite cat</h1>
                    <input type="text" class="form-control" v-model="search" placeholder="Search for a cat">
                    
                  </div>
                </div>
              </div>
            </section>
            <section class="container-fluid section section1 mb-5">

              <div class="row">
                <div class="col-12 col-sm-6 col-md-6 col-lg-6 col-xl-4" v-for="(cat, index) in filteredList" :key="index" :class="even(index)">
                  <div class="images">
                    <img :src="cat.image.url" alt="" :id="cat.id" class="imageCats rounded" v-if="cat.image && cat.id!='pers'" >
                    <img :src="'src/assets/logoCats.png'" alt="placeholder" :id="cat.id" class="imageCats rounded" v-else>
                    <h3 class="d-block px-3 position-absolute text-center nameCats font-primary gluten" :model="cat.name">{{cat.name}}
                      <span class="d-block h6 alternateName" style="">{{cat.alt_names}}</span>
                    </h3>
                  </div>
                  <div class="description d-flex flex-column">
                    <p class="descriptionCats mb-auto pt-2 text-justify">
                      {{cat.description}}
                    </p>
                    <button @click="isOpenM(index)" class="btn bg-primary-dark text-white  ">
                        Read more
                    </button>
                    <div class="row m-0 px-0 pt-2" v-show="isOpen[index] == true" >
                      <p class="temperamentCats m-0 pb-2 text-justify">Temperament: {{cat.temperament}}</p>
                        
                      <InfoCats 
                        :weightImperial="cat.weight.imperial"
                        :weightMetric="cat.weight.metric"
                        :cfaUrl="cat.cfa_url"
                        :vetstreetUrl="cat.vetstreet_url"
                        :vcahospitalsUrl="cat.vcahospitals_url"
                        :wikipediaUrl="cat.wikipedia_url"
                        :origin="cat.origin"
                        :lifespan="cat.life_span"
                        :rareCats="cat.rare"
                        :hairlessCats="cat.hairless"
                        :suppressedTailCats="cat.suppressed_tail"
                        :shortLegsCats="cat.short_legs"
                        :hypoallergenicCats="cat.hypoallergenic"
                        :naturalCats="cat.natural"
                      />
                      <CatsCharacteristics 
                        :affection_level="cat.affection_level"
                        :child_friendly="cat.child_friendly"
                        :dog_friendly="cat.dog_friendly"
                        :energy_level="cat.energy_level"
                        :grooming="cat.grooming"
                        :adaptability="cat.adaptability"
                        :intelligence="cat.intelligence"
                        :shedding_level="cat.shedding_level"
                        :social_needs="cat.social_needs"
                        :health_issues="cat.health_issues"
                        :stranger_friendly="cat.stranger_friendly"
                        :vocalisation="cat.vocalisation"
                      />
                      
                    </div>
                  </div>
                </div>
              </div>
            </section>

            <img alt="Vue logo" class="logo underlineRotateContact" src="./assets/header.svg" height="20" />
            <Section2/>
            <img alt="Vue logo" class="logo underlineContact" src="./assets/header.svg" height="20" />
        </main>
        <Footer />
        <div class="scrollTop position-fixed">
          <a href="#search" class="d-block">
            <i class="uis uis-arrow-circle-up font-primary-light unicons"></i>
          </a>
        </div>
        <div class="scrollBottom position-fixed">
          <a href="#contact" class="d-block">
            <i class="uis uis-arrow-circle-down font-primary-light  unicons"></i>
          </a>
        </div>
    </div>
</template>

<script>
import { CollapseTransition } from "@ivanv/vue-collapse-transition"
import HelloWorld from './components/HelloWorld.vue';
import Header from './components/Header.vue';
import Section1 from './components/Section1.vue';
import Section2 from './components/Contact2.vue';
import InfoCats from './components/InfoCats.vue';
import CatsCharacteristics from './components/CatsCharacteristics.vue';
import Footer from './components/Footer.vue';

import TheWelcome from './components/TheWelcome.vue';
import axios from "axios";

export default {
  name: "app",
  components: {
    HelloWorld,
    TheWelcome,
    Header,
    Section2,
    InfoCats,
    CatsCharacteristics,
    Footer,
  },
  data(){
    return {
      search:'',
      searchAlternate:'',
      isOpen: [
        false, false, false, false, false, false, false, false, false, false, 
        false, false, false, false, false, false, false, false, false, false, 
        false, false, false, false, false, false, false, false, false, false, 
        false, false, false, false, false, false, false, false, false, false, 
        false, false, false, false, false, false, false, false, false, false, 
        false, false, false, false, false, false, false, false, false, false, 
        false, false, false, false, false, false, false, false
      ],
      URL: "https://api.thecatapi.com/v1/",
      apiKey: '4d3e0448-10d7-419b-a33d-f84ecbb0caf4',
      result: [],

      weight:{},
      id:"",
      image: {},
      name:"",
      cfa_url:"",
      vetstreet_url:"",
      vcahospitals_url:"",
      temperament:"",
      origin:"",
      country_codes:"",
      country_code:"",
      description:"",
      life_span:"",
      indoor:"",
      lap:0,
      alt_names:"",
      adaptability:0,
      affection_level: 0,
      child_friendly: 0,
      dog_friendly: 0,
      energy_level: 0,
      grooming: 0,
      health_issues: 0,
      intelligence: 0,
      shedding_level: 0,
      social_needs: 0,
      stranger_friendly: 0,
      vocalisation: 0,
      experimental: 0,
      hairless: 0,
      natural: 0,
      rare: 0,
      rex: 0,
      suppressed_tail: 0,
      short_legs: 0,
      wikipedia_url: "",
      hypoallergenic: 0,
      reference_image_id: "",
    }
  },
  computed:{
    filteredList(){
      return this.result.filter(post => {
        return post.name.toLowerCase().includes(this.search.toLowerCase())
      })
    },
  },

  created() {
    this.getCatsApi();
  },

  methods: {
    isOpenM(index){
      this.isOpen[index] = !this.isOpen[index];
      return this.isOpen[index];
    },

    even(index){
      const classEven = index % 2 ? 'even' : 'odd';
      return classEven;
    },

    getZmienne(data){
      for (const key in data) {
        if (Object.hasOwnProperty.call(data, key)) {
          const element = data[key];
          this.weight = element.weight;
          this.id = element.id;
          this.name = element.name;
          this.cfa_url = element.cfa_url;
          this.image = element.image;
          this.vetstreet_url = element.vetstreet_url;
          this.vcahospitals_url = element.vcahospitals_url;
          this.temperament = element.temperament;
          this.origin = element.origin;
          this.country_codes = element.country_codes;
          this.country_code = element.country_code;
          this.description = element.description;
          this.life_span = element.life_span;
          this.indoor = element.indoor;
          this.lap = element.lap;
          this.alt_names = element.alt_names;
          this.adaptability = element.adaptability;
          this.affection_level = element.affection_level;
          this.child_friendly = element.child_friendly;
          this.dog_friendly = element.dog_friendly;
          this.energy_level = element.energy_level;
          this.grooming = element.grooming;
          this.health_issues = element.health_issues;
          this.intelligence = element.intelligence;
          this.shedding_level = element.shedding_level;
          this.social_needs = element.social_needs;
          this.stranger_friendly = element.stranger_friendly;
          this.vocalisation = element.vocalisation;
          this.experimental = element.experimental;
          this.hairless = element.hairless;
          this.natural = element.natural;
          this.rare = element.rare;
          this.rex = element.rex;
          this.suppressed_tail = element.suppressed_tail;
          this.short_legs = element.short_legs;
          this.wikipedia_url = element.wikipedia_url;
          this.hypoallergenic = element.hypoallergenic;
          this.reference_image_id  = element.reference_image_id;
        }
      }
    },

    getImage(data){
      const arr = data;
      const arr1 = [];
      for (let index = 0; index < arr.length; index++) {
        const element = arr[index].image;
        if (element !== undefined) {
          arr1.push(element);
        } else {
          arr1.push({});
        }
      }
      return arr1;
    },

    async getCatsApi(){
      const config = {
        method: 'get',
        url: `${this.URL}breeds/`,
        headers: { 
          'Content-Type': 'application/json', 
          'x-api-key': `${this.apiKey}`
        }
      };
      await axios(config)
          .then(res => {
            if (res.status == 200) {
              this.result = res.data;
              this.image = this.getImage(res.data);
            } else {
              console.log(res.statusText);
            }
          })
          .catch(err => {
            console.log(err);
          })
      await this.getZmienne(await this.result);
    }
  },

}
</script>
<style src="vue-multiselect/dist/vue-multiselect.css"></style>
<style lang="scss">
@import './assets/base.css';
@import './scss/app.scss';
</style>
