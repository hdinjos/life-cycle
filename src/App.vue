<template>
  <div class="row">
    <a-row>
      <a-col
        v-for="(col, index) in gridTwo" :key="col"
        :class="index % 2 === 0 ? 'col col-orange' : 'col col-red'"
        :span="24/gridTwo.length"
      >
        {{col}}
      </a-col>
    </a-row>
    <a-row>
      <a-col
        v-for="(col, index) in gridTree" :key="col"
        :class="index % 2 === 0 ? 'col col-orange' : 'col col-red'"
        :span="24/gridTree.length"
      >
        {{col}}
      </a-col>
    </a-row>
    <a-row>
      <a-col
        v-for="(col, index) in gridFour" :key="col"
        :class="index % 2 === 0 ? 'col col-orange' : 'col col-red'"
        :span="24/gridFour.length"
      >
        {{col}}
      </a-col>
    </a-row>
  </div>
</template>

<script>
export default {
  name: "App",
  data: () => {
    return {
      gridTwo: ['Col 1', 'Col 2'],
      gridTree: ['Col 1', 'Col 2', 'Col 3'],
      gridFour: ['Col 1', 'Col 2', 'Col 3', 'Col 4']
    }
  },
  // computed: {
  //   two: function(){
  //     return this.grid/this.gridTwo.length; 
  //   }
  // }
};
</script>

<style>
  .row {
    background-color: pink;
    width: 100%;
    height: 100%;
  }
  .col {
    width: 50px;
    height: 50px;
    text-align: center;
    padding-top: 15px;
    color:#fff;
    margin-bottom: 10px;
  }
  .col-orange {
    background-color: orange;
  }
  .col-red {
    background-color: red;
  }
</style>
