<template>
    <el-row>
      <el-col style="margin-right: -15px" :md="1" :sm="23" :xs="23">
        <div class="left">
          <a href="https://github.com/">
            <svg  height="32" viewBox="0 0 16 16" version="1.1" width="32" aria-hidden="true"><path fill="#ffffff" fill-rule="evenodd" d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"></path></svg>
          </a>
        </div>
      </el-col >
      <el-col :md="21" class="hidden-sm-and-down">
        <div class="middle">
          <div class="in">
            <input type="text" :class="isActive"
                   @click="big" @keyup.enter="enterSearch"
                   @blur="small" v-model="key"
                   placeholder="Search or jump to…">
            <img src="../../assets/search-key-slash.svg" alt=""
            v-show="isActive == 'input'">
            <a href="https://github.com/pulls">Pull requests</a>
            <a href="https://github.com/issues">Issues</a>
            <a href="https://github.com/marketplace">Marketplace</a>
            <a href="https://github.com/explore">Explore</a>
          </div>
        </div>
      </el-col>
      <el-col :md="2" :sm="1" :xs="1">
        <div class="right">
          <el-row :gutter="0">
            <el-col :md="6">
              <i class="el-icon-message-solid"></i>
            </el-col>
            <el-col :md="8" class="hidden-md-and-down">
              <div class="add">
                <i class="el-icon-plus"></i>
                <i class="el-icon-caret-bottom"></i>
              </div>
            </el-col>
            <el-col :md="10" class="hidden-md-and-down">
              <div class="account">
                <i class="el-icon-s-custom"></i>
                <i class="el-icon-caret-bottom"></i>
              </div>
            </el-col>
          </el-row>
        </div>
      </el-col>
    </el-row>
</template>

<script>
  export default {
    name: "myHeader",
    data() {
      return {
       isActive: 'input',
        key: ''
      }
    },
    components: {
    },
    methods: {
      big(){
        this.isActive = 'input_big'
      },
      small(){
        this.isActive = 'input'
      },
      enterSearch() {
        this.$emit('search',this.key)
      }
    }
  }
</script>

<style scoped lang="less">
.el-row {
  .left {
    a {
      img {
        width: 30px;
        height: 30px;
      }
    }
  }
  .middle {
    .in {
      position: relative;
      .input {
        color: #ffffff;
        width: 273px;
        height: 30px;
        background-color: rgb(63, 68, 72);
        border: 0;
        border-radius: 2px;
        outline: none;
        padding: 0 15px;
      }
      .input_big {
        width: 460px;
        height: 30px;
        border: 0;
        outline: none;
        padding: 0 15px;
      }
      img {
        position: absolute;
        left: 275px;
        top: 5px;
      }
      a {
        margin-left: 16px;
        color: #fff;
        font-size: 14px;
        font-weight: 600;
      }

    }
  }
  .right {
    line-height: 30px;
      i {
        color: #ffffff;
      }
      .add {
      }
  }
}
</style>
