<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div>
      <a-button type="primary" @click="changeMode('red')"> 测试 </a-button>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  methods: {
    // 调用方法
    changeMode(color) {
      window.less
        .modifyVars({
          "@primary-color": color,
          "@link-color": color,
          "@btn-primary-bg": color,
        })
        .then(() => {
          console.log("成功");
        })
        .catch((error) => {
          alert("失败");
          console.log(error);
        });
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="less">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
