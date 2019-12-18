<template>
  <el-row :gutter="0">
    <el-col :md="2"><div class="vide"></div></el-col>
    <el-col :md="20"><div class="show">
      <el-row>
        <el-col :md="12">
          <el-row>
            <el-col :md="4">
              <h6>© 2019 GitHub, Inc.</h6>
            </el-col>
            <el-col :md="4">
              <a href="">Terms</a>
            </el-col>
            <el-col :md="4">
              <a href="">Privacy</a>
            </el-col>
            <el-col :md="4">
              <a href="">Security</a>
            </el-col>
            <el-col :md="4">
              <a href="">Status</a>
            </el-col>
            <el-col :md="4">
              <a href="">Help</a>
            </el-col>
          </el-row>
        </el-col>
        <el-col :md="1" class="hidden-sm-and-down">
          <img src="../../assets/logo-bottom.png" alt="">
        </el-col>
        <el-col :md="11">
          <el-row :gutter="5">
            <el-col :md="5">
              <a href="">Contact GitHub</a>
            </el-col>
            <el-col :md="4">
              <a href="">Pricing</a>
            </el-col>
            <el-col :md="5">
              <a href="">API</a>
            </el-col>
            <el-col :md="5">
              <a href="">Training</a>
            </el-col>
            <el-col :md="5">
              <a href="">Blog</a>
            </el-col>
          </el-row>
        </el-col>
      </el-row>
    </div></el-col>
    <el-col :md="2"><div class="vide"></div></el-col>
  </el-row>
<!--  <el-row>-->
<!--    <el-col :md="0">-->
<!--      <el-row>-->
<!--        <el-col :md="4">-->
<!--          <h6>© 2019 GitHub, Inc.</h6>-->
<!--        </el-col>-->
<!--        <el-col :md="4">-->
<!--          <a href="">Terms</a>-->
<!--        </el-col>-->
<!--        <el-col :md="4">-->
<!--          <a href="">Privacy</a>-->
<!--        </el-col>-->
<!--        <el-col :md="4">-->
<!--          <a href="">Security</a>-->
<!--        </el-col>-->
<!--        <el-col :md="4">-->
<!--          <a href="">Status</a>-->
<!--        </el-col>-->
<!--        <el-col :md="4">-->
<!--          <a href="">Help</a>-->
<!--        </el-col>-->
<!--      </el-row>-->
<!--    </el-col>-->
<!--    <el-col :md="0" class="hidden-sm-and-down">-->
<!--      <img src="../../assets/logo-bottom.png" alt="">-->
<!--    </el-col>-->
<!--    <el-col :md="24">-->
<!--      <el-row :gutter="5">-->
<!--        <el-col :md="5">-->
<!--          <a href="">Contact GitHub</a>-->
<!--        </el-col>-->
<!--        <el-col :md="4">-->
<!--          <a href="">Pricing</a>-->
<!--        </el-col>-->
<!--        <el-col :md="5">-->
<!--          <a href="">API</a>-->
<!--        </el-col>-->
<!--        <el-col :md="5">-->
<!--          <a href="">Training</a>-->
<!--        </el-col>-->
<!--        <el-col :md="5">-->
<!--          <a href="">Blog</a>-->
<!--        </el-col>-->
<!--      </el-row>-->
<!--    </el-col>-->
<!--  </el-row>-->
</template>

<script>
  export default {
    name: "Bottom"
  }
</script>

<style scoped>
  h6 {
    display: inline;
    font-weight: 400;
    color: rgb(88, 96, 105);
  }
  a {
    text-decoration: none;
    color: #0366d6;
    font-size: 12px;
  }
  img {
  }
  .vide {
    background-color: transparent;
  }
  .show {
    background-color: pink;
  }
</style>
