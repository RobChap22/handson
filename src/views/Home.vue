<template>
  <div>
    <div class="guys" >
      <img
        v-for='(guy, i) in newguys'
        :key='i'
        @click='onClick(guy)'
        :src='guy.imgpath'
      >
    </div>
    <div class="question" >
      <h2>Which new guy is {{ rando }}?</h2>
    </div>
    <p id='score'>Correct: {{ score }}</p>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';


export default Vue.extend({
  created() {
    this.randoGenerate();
  },
  name: 'Home',
  data: () => {
  return {
    newguys: [
      {
        name: 'Rob',
        imgpath: '/img/rob.jpg',
        Rob: true,
        Julien: false,
        French: false,
        English: true,
        married: false,
        taller: false
      },
      {
        name: 'Julien',
        imgpath: '/img/julien.png',
        Rob: true,
        Julien: true,
        French: true,
        English: false,
        married: true,
        taller: true
      }
    ],
    info: ['Rob', 'Julien', 'French', 'English', 'married', 'taller'],
    rando: '',
    score: 0
  }
  },
  components: {

  },
  methods: {
    randoGenerate() {
      this.rando = this.info[Math.floor(Math.random()*this.info.length)]
    },
    onClick(guy) {
      console.log(guy.name);

      if (guy[this.rando]) {
        this.score += 1;
      }
      this.randoGenerate();
    },
  }
});
</script>

<style lang='scss'>

  .guys {
    display: flex;
    justify-content: center;
    margin: 20px;
    padding: 30px;
  }

  img {
    height: 300px;
    border-radius: 50%;
    margin: 30px;
    box-shadow: 0 0 2px #b8c1ec;
    transition: 0.5s;
    &:hover {
      box-shadow: 0 0 4px 1px #b8c1ec;
    }
  }

  #score {
    font-size: 60px;
    font-weight: 900;
    color: #eebbc3;
  }



</style>
