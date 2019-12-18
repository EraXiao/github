<template>
  <nav>
    <div></div>
    <a href="#" class="sp" style="color: black;font-weight: 500">
      Repositories
      <span>3M+</span>
    </a>
    <a href="#">
      Code
      <span>137M+</span>
    </a>
    <a href="#">
      Commits
      <span>113M+</span>
    </a>
    <a href="#">
      Issues
      <span>3M+</span>
    </a>
    <a href="#">
      Packages
      <span>470</span>
    </a>
    <a href="#">
      Marketplace
      <span>250</span>
    </a>
    <a href="#">
      Topics
      <span>1K</span>
    </a>
    <a href="#">
      Wikis
      <span>292K</span>
    </a>
    <a href="#">
      Users
      <span>82K</span>
    </a>
  </nav>
</template>

<script>
  export default {
    name: "navTop"
  }
</script>

<style scoped lang="less">
  nav {
    margin: 0;
    padding: 0;
    height: 314px;
    border: 1px solid rgb(209, 213, 218);
    text-align: left!important;
    position: relative;
    div {
      position: absolute;
      left: 0px;
      top: 0;
      width: 2px;
      height: 34px;
      background-color: #e36209;
    }
  }
  nav>a {
    padding-left: 10px;
    display: block;
    height: 34px;
    line-height: 34px;
    border-bottom: 1px solid rgb(209, 213, 218);
    text-decoration: none;
    font-size: 14px;
    color: rgb(3, 102, 216);
    span {
      display: inline-block;
      padding: 2px 4px;
      font-size: 12px;
      font-weight: 500;
      line-height: 1;
      float: right;
      margin-right: 5px;
      margin-top: 10px;
      background-color:#6a737d;
      color: white;
      border-radius: 20px;
    }
  }
  nav>a:hover {
    color: black;
    background-color: rgb(246, 248, 250);
  }
</style>
