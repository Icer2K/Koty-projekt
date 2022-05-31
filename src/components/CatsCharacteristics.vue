<template>
    <div class="col-7 p-0">
        <div class="d-flex justify-content-between p-0">
            <div>Affection level {{affection_level}}</div>
            <div>
            <img src="src/assets/star-fill.svg" alt="" v-for="item in affection_level" :key="item">
            <img src="src/assets/star.svg" alt="" v-for="item in (5-affection_level)" :key="item">
            </div>
        </div>

        <div class="d-flex justify-content-between p-0">
            <div>child friendly</div>
            <div>
            <img src="../assets/star-fill.svg" alt="" v-for="item in child_friendly" :key="item">
            <img src="../assets/star.svg" alt="" v-for="item in (5-child_friendly)" :key="item">
            </div>
        </div>

        <div class="d-flex justify-content-between p-0">
            <div>dog friendly</div>
            <div>
            <img src="../assets/star-fill.svg" alt="" v-for="item in dog_friendly" :key="item">
            <img src="../assets/star.svg" alt="" v-for="item in (5-dog_friendly)" :key="item">
            </div>
        </div>

        <div class="d-flex justify-content-between p-0">
            <div>energy level</div>
            <div>
            <img src="../assets/star-fill.svg" alt="" v-for="item in energy_level" :key="item">
            <img src="../assets/star.svg" alt="" v-for="item in (5-energy_level)" :key="item">
            </div>
        </div>

        <div class="d-flex justify-content-between p-0">
            <div>grooming</div>
            <div>
            <img src="../assets/star-fill.svg" alt="" v-for="item in grooming" :key="item">
            <img src="../assets/star.svg" alt="" v-for="item in (5-grooming)" :key="item">
            </div>
        </div>

        <div class="d-flex justify-content-between p-0">
            <div>Adaptation</div>
            <div>
            <img src="../assets/star-fill.svg" alt="" v-for="item in adaptability" :key="item">
            <img src="../assets/star.svg" alt="" v-for="item in (5-adaptability)" :key="item">
            </div>
        </div>

        <div class="d-flex justify-content-between p-0">
            <div>intelligence</div>
            <div>
            <img src="../assets/star-fill.svg" alt="" v-for="item in intelligence" :key="item">
            <img src="../assets/star.svg" alt="" v-for="item in (5-intelligence)" :key="item">
            </div>
        </div>

        <div class="d-flex justify-content-between p-0">
            <div>shedding of hair</div>
            <div>
            <img src="../assets/star-fill.svg" alt="" v-for="item in shedding_level" :key="item">
            <img src="../assets/star.svg" alt="" v-for="item in (5-shedding_level)" :key="item">
            </div>
        </div>

        <div class="d-flex justify-content-between p-0">                          
            <div>social needs</div>
            <div>
            <img src="../assets/star-fill.svg" alt="" v-for="item in social_needs" :key="item">
            <img src="../assets/star.svg" alt="" v-for="item in (5-social_needs)" :key="item">
            </div>
        </div>
        <div class="d-flex justify-content-between p-0">
            <div>friendly</div>
            <div>
            <img src="../assets/star-fill.svg" alt="" v-for="item in health_issues" :key="item">
            <img src="../assets/star.svg" alt="" v-for="item in (5-health_issues)" :key="item">
            </div>
        </div>

        <div class="d-flex justify-content-between p-0">
            <div>health problems</div>
            <div>
            <img src="../assets/star-fill.svg" alt="" v-for="item in stranger_friendly" :key="item">
            <img src="../assets/star.svg" alt="" v-for="item in (5-stranger_friendly)" :key="item">
            </div>
        </div>

        <div class="d-flex justify-content-between p-0">
            <div>stranger friendly</div>
            <div>
            <img src="../assets/star-fill.svg" alt="" v-for="item in stranger_friendly" :key="item">
            <img src="../assets/star.svg" alt="" v-for="item in (5-stranger_friendly)" :key="item">
            </div>
        </div>

        <div class="d-flex justify-content-between p-0">
            <div>stranger friendly</div>
            <div>
            <img src="../assets/star-fill.svg" alt="" v-for="item in stranger_friendly" :key="item">
            <img src="../assets/star.svg" alt="" v-for="item in (5-stranger_friendly)" :key="item">
            </div>
        </div>

        <div class="d-flex justify-content-between p-0">
            <div>Excessive meowing</div>
            <div>
            <img src="../assets/star-fill.svg" alt="" v-for="item in vocalisation" :key="item">
            <img src="../assets/star.svg" alt="" v-for="item in (5-vocalisation)" :key="item">
            </div>
        </div>
    </div>
</template>

<script setup>
defineProps({
  affection_level: {
    type: Number
  },
  child_friendly: {
    type: Number
  },
  dog_friendly: {
    type: Number
  },
  energy_level:{
      type: Number
  },
  grooming: {
    type: Number
  },
  adaptability: {
    type: Number
  },
  intelligence: {
    type: Number
  },
  shedding_level: {
    type: Number
  },
  social_needs: {
    type: Number
  },
  health_issues: {
    type: Number
  },
  stranger_friendly: {
    type: Number
  },
  vocalisation: {
    type: Number
  },                
})
</script>