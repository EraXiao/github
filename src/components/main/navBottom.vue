<template>
  <nav>
    <span>Languages</span>
    <div class="lg-bottom">
      <a href="">
        JavaScript
        <span>963,979</span>
      </a>
      <a href="">
        Java
        <span>330,013</span>
      </a>
      <a href="">
        C++
        <span>268,704</span>
      </a>
      <a href="">
        Python
        <span>97,456</span>
      </a>
      <a href="">
        C#
        <span>48,640</span>
      </a>
      <a href="">
        Assembly
        <span>40,644</span>
      </a>
      <a href="">
        C
        <span>32,182</span>
      </a>
      <a href="">
        HTML
        <span>20,522</span>
      </a>
      <a href="">
        TypeScript
        <span>19,097</span>
      </a>
      <a href="">
        Swift
        <span>9,979</span>
      </a>
    </div>
  </nav>
</template>

<script>
  export default {
    name: "navBottom"
  }
</script>

<style scoped lang="less">
  nav {
    margin: 0;
    padding: 0;
    height: 343px;
    border: 1px solid rgb(209, 213, 218);
  }
  nav>span {
    display: block;
    padding-left: 16px;
    text-align: left;
    line-height: 50px;
    height: 42px;
    font-size: 14px;
    font-weight: 600;
  }
  nav>div {
    margin: 0 15px;
    height: 276px;
  }
  nav>div>a {
    padding: 0 8px;
    text-align: left!important;
    display: block;
    height: 28px;
    line-height: 28px;
    font-size: 12px;
    color: rgb(88, 98, 110);
    text-decoration: none;
    span {
      float: right;
      font-weight: 500;
    }
  }
  nav>div>a:hover {
    border-radius: 5px;
    background-color: rgb(234, 236, 239);
  }
</style>
