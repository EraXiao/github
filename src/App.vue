<template>
  <div id="app">
    <el-container>
      <el-header>
        <my-header @search="search"></my-header>
      </el-header>
      <el-main  v-show="total">
        <el-row>
          <el-col :md="4" :sm="4" :xs="1">
            <div style="background-color: transparent;color: transparent">1</div>
          </el-col>
          <el-col :md="16" :sm="20" :xs="23" style="margin-left: -33px">
            <div class="main">
              <el-row :gutter="22">
                <el-col :md="6" class="hidden-sm-and-down">
                  <el-row>
                    <el-col>
                      <div class="left">
                        <!--            左上的nav-->
                        <div class="nav-top">
                          <nav-top/>
                        </div>
                        <!--              右下的nav-->
                        <div class="nav-bottom">
                          <nav-bottom/>
                        </div>
                        <div class="nav">
                          <a href="">
                            Advanced search
                          </a>
                          <a href="">
                            Cheat sheet
                          </a>
                        </div>
                      </div>
                    </el-col>
                  </el-row>
                </el-col>
                <el-col :md="17">
                  <div class="right">
                    <div class="right-top">
                      <p class="left">Showing 3,185,718 available repository results</p>
                      <el-dropdown>
                        <el-button>
                          Sort:<span style="font-weight: 700">Best match</span><i class="el-icon-arrow-down el-icon--right"></i>
                        </el-button>
                        <el-dropdown-menu slot="dropdown">
                          <el-dropdown-item>Best match</el-dropdown-item>
                          <el-dropdown-item>Most stars</el-dropdown-item>
                          <el-dropdown-item>Fewest stars</el-dropdown-item>
                          <el-dropdown-item>Most forks</el-dropdown-item>
                          <el-dropdown-item>Fewest forks</el-dropdown-item>
                          <el-dropdown-item>Recently updated</el-dropdown-item>
                          <el-dropdown-item>Least recently updated</el-dropdown-item>
                        </el-dropdown-menu>
                      </el-dropdown>
                    </div>
                    <div class="right-bottom" v-for="(child,index) in childList" :key="index">
                      <item-project :child="child"/>
                    </div>
                    <el-row>
                      <el-col :md="7">
                        <div style="color: transparent">1</div>
                      </el-col>
                      <el-col :md="17">
                        <div>
                          <el-pagination
                                  layout="prev, pager, next"
                                  :total="1000"
                                  prev-text="Previous"
                                  next-text="Next"
                                  @current-change="change"
                                  @prev-click="previous"
                                  @next-click="next">
                          </el-pagination>
                        </div>
                      </el-col>
                    </el-row>
                  </div>
                </el-col>
              </el-row>
            </div>
          </el-col>
          <el-col :md="4" class="hidden-sm-and-down">
            <div style="background-color: transparent;color: transparent">2</div>
          </el-col>
        </el-row>
      </el-main>
      <el-footer v-show="total">
        <te></te>
      </el-footer>
    </el-container>
  </div>
</template>
<script>
  import myHeader from "./components/header/myHeader";
  import navTop from "./components/main/navTop";
  import navBottom from "./components/main/navBottom";
  import itemProject from "./components/main/itemProject";
  import te from "./components/main/te";
  export default {
    data(){
      return {
        childList: [],
        query: {
          q: '',
          page: 1,
          per_page: 10
        },
        total: ''
      }
    },
    components: {
      myHeader,
      navTop,
      navBottom,
      itemProject,
      te
    },
    methods: {
      search(key){
        this.query.q = key
        this.getList()
      },
      async getList(){
        let List = await this.axios.get('https://api.github.com/search/repositories',{params:this.query})
        this.childList = List.data.items
        this.total = List.data.total_count
      },
      next(){
        this.query.page += 1
        this.getList()
      },
      previous(){
        this.query.page -= 1
        this.getList()
      },
      change(currentPage){
        this.query.page = currentPage
        this.getList()
      }
    },
  }
</script>
<style lang="less">
  @import "assets/css/style";
</style>
