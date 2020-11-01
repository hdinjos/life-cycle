<template>
  <div class="row">
    <h1>grid system</h1>
    <a-row>
      <a-col
        v-for="(col, index) in gridTwo"
        :key="col"
        :class="index % 2 === 0 ? 'col col-orange' : 'col col-red'"
        :span="24 / gridTwo.length"
      >
        {{ col }}
      </a-col>
    </a-row>
    <a-row>
      <a-col
        v-for="(col, index) in gridTree"
        :key="col"
        :class="index % 2 === 0 ? 'col col-orange' : 'col col-red'"
        :span="24 / gridTree.length"
      >
        {{ col }}
      </a-col>
    </a-row>
    <a-row>
      <a-col
        v-for="(col, index) in gridFour"
        :key="col"
        :class="index % 2 === 0 ? 'col col-orange' : 'col col-red'"
        :span="24 / gridFour.length"
      >
        {{ col }}
      </a-col>
    </a-row>
    <h1>Sub align</h1>
    <a-row type="flex" justify="center" align="middle">
      <a-col
        style="height: 100px; width: 200px"
        class="col col-orange"
        :span="4"
        >Col 1</a-col
      >
      <a-col class="col col-red" :span="4">Col 2</a-col>
      <a-col class="col col-orange" :span="4">Col 3</a-col>
    </a-row>
    <a-divider orientation="left"> kolom persentase </a-divider>
    <a-row type="flex">
      <a-col class="col col-orange" :flex="1">Col 1</a-col>
      <a-col class="col col-red" :flex="2">Col 1</a-col>
    </a-row>
    <a-divider orientation="left"> fill rest </a-divider>
    <a-row type="flex">
      <a-col flex="200px" class="col col-orange">Col 1</a-col>
      <a-col flex="auto" class="col col-red">Col 2</a-col>
    </a-row>
    <a-divider orientation="left"> raw flex style </a-divider>
    <a-row type="flex">
      <a-col flex="1 1 200px" class="col col-orange">Col 1</a-col>
      <a-col flex="1 1 200px" class="col col-red">Col 2</a-col>
    </a-row>
    <h1>Gutter</h1>

    <a-row :gutter="16">
      <a-col class="gutter-row" :span="6">
        <div class="gutter-box">col-6</div>
      </a-col>
      <a-col class="gutter-row" :span="6">
        <div class="gutter-box">col-6</div>
      </a-col>
      <a-col class="gutter-row" :span="6">
        <div class="gutter-box">col-6</div>
      </a-col>
      <a-col class="gutter-row" :span="6">
        <div class="gutter-box">col-6</div>
      </a-col>
    </a-row>
    <h1>Offset</h1>
    <a-row>
      <a-col class="col col-orange" :span="8">Col 8</a-col>
      <a-col class="col col-red" :span="8" offset="8">Col 8</a-col>
    </a-row>
    <a-row>
      <a-col class="col col-red" :span="8" offset="8">Col 8</a-col>
    </a-row>

    <a-row>
      <a-col
        class="col col-orange"
        :xs="{ span: 5 }"
        :sm="{ span: 7 }"
        :md="{ span: 8 }"
        >Col 1</a-col
      >
      <a-col
        class="col col-red"
        :xs="{ span: 11, offset: 1 }"
        :sm="{ span: 7, offset: 1 }"
        :md="{ span: 6, offset: 1 }"
        >Col 2</a-col
      >
      <a-col
        class="col col-orange"
        :xs="{ span: 5, offset: 1 }"
        :sm="{ span: 7, offset: 1 }"
        :md="{ span: 8, offset: 1 }"
        >Col 3</a-col
      >
    </a-row>

    <h1>pull and push change order easily</h1>
    <a-row>
      <a-col :span="4" :push="8" class="col col-orange">Col 1</a-col>
      <a-col :span="8" :pull="4" class="col col-red">Col 2</a-col>
    </a-row>
  </div>
</template>

<script>
export default {
  data: () => {
    return {
      gridTwo: ["Col 1", "Col 2"],
      gridTree: ["Col 1", "Col 2", "Col 3"],
      gridFour: ["Col 1", "Col 2", "Col 3", "Col 4"],
    };
  },
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
  color: #fff;
  margin-bottom: 10px;
}
.col-orange {
  background-color: orange;
}
.col-red {
  background-color: red;
}
/* .gutter-example >>> .ant-row > div {
  background: transparent;
  border: 0;
  } */
.gutter-box {
  background: #00a0e9;
  /* padding: 5px 0 */
}
</style>