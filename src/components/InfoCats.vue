<template>
    <div class="col-5 p-0">
        Weight:
        <p class="weightCats m-0">
          {{weightImperial}} ounce
        </p>
        <p class="weightCats m-0">
          {{weightMetric}} kg
        </p>
        <p class="cfaCats m-0" v-if="cfaUrl != undefined">
          <a :href="cfaUrl">Learn more at CFA</a>
        </p>
        <p class="characteristicCats m-0" v-if="vetstreetUrl != undefined">
          <a :href="vetstreetUrl">Breed characteristics</a>
        </p>
        <p class="historyCats m-0" v-if="vcahospitalsUrl != undefined">
          <a :href="vcahospitalsUrl">History & Trivia</a>
        </p>
        <p class="wikipediaCats m-0" v-if="wikipediaUrl != undefined">
          <a :href="wikipediaUrl">Wikipedia</a>
        </p>
        <p class="originCats m-0">
          Origins: {{origin}}
        </p>
        <p class="lifespanCats m-0">Length of life: {{lifespan}}</p>
        <p class="rareCats m-0" v-if="rareCats == 1">Very rare cat</p>
        <p class="hairlessCats m-0" v-if="hairlessCats == 1">Hairless cat</p>
        <p class="suppressedTailCats m-0" v-if="suppressedTailCats == 1">Short tail</p>
        <p class="shortLegsCats m-0" v-if="shortLegsCats == 1">Short legs</p>
        <p class="hypoallergenicCats m-0" v-if="hypoallergenicCats == 1">Hypoallergenic cat</p>
        <p class="naturalCats m-0" v-if="naturalCats == 1">Living in nature</p>
    </div>
</template>

<script setup>
defineProps({
  weightImperial: {
    type: String
  },
  weightMetric: {
    type: String
  },
  cfaUrl: {
    type: String
  },
  vetstreetUrl: {
    type: String
  },
  vcahospitalsUrl: {
    type: String
  },
  wikipediaUrl: {
    type: String
  },
  lifespan: {
    type: String
  },
  origin: {
    type: String
  },
  hairlessCats: {
    type: Number
  },
  suppressedTailCats: {
    type: Number
  },
  shortLegsCats: {
    type: Number
  },
  hypoallergenicCats: {
    type: Number
  },
  naturalCats: {
    type: Number
  },       
  info: {
    type: String
  },
  rareCats:{
    type: Number
  },
  clas: {
      type: String,
  },
  units: {
    type: String,
  }
})
</script>