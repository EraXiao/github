<template>
  <div class="item">
<!--    标题-->
    <a :href="child.html_url">
      <div style="display: inline;margin-right: 5px">
        <svg height="16" style="color: #6a737d" class="octicon octicon-repo" viewBox="0 0 12 16" version="1.1" width="12" aria-hidden="true"><path fill-rule="evenodd" d="M4 9H3V8h1v1zm0-3H3v1h1V6zm0-2H3v1h1V4zm0-2H3v1h1V2zm8-1v12c0 .55-.45 1-1 1H6v2l-1.5-1.5L3 16v-2H1c-.55 0-1-.45-1-1V1c0-.55.45-1 1-1h10c.55 0 1 .45 1 1zm-1 10H1v2h2v-1h3v1h5v-2zm0-10H2v9h9V1z"></path></svg>
      </div>
      {{child.name}}
    </a>
<!--    描述-->
    <p>{{child.description}}</p>
<!--    底部信息-->
    <div class="itemBottom">
      <a :href="child.stargazers_url"><i class="el-icon-star-on"></i>{{starNumber}}</a>
      <p>{{child.language}}</p>
      <p>{{dateChange}}</p>
  </div>
  </div>
</template>

<script>
  export default {
    name: "itemProject",
    props: [
      "child"
    ],
    computed: {
        starNumber() {
            let num = this.child.stargazers_count
            return num = num<1000 ? num : (num*0.001).toFixed(1)+'k'
        },
        dateChange(){
            let date = this.child.updated_at
            var monthArr = new Array("Jan","Feb","Mar","Apr","May","Jun","Jul","Aug","Spt","Oct","Nov","Dec");
            var suffix = new Array("st","nd","rd","th");

            var month = monthArr[date.slice(5, 7)-1]; //月
            var ddate = date.slice(8, 10); //日

            if(ddate % 10 < 1 || ddate % 10 > 3) {
                ddate = ddate + suffix[3];
            }else if(ddate % 10 == 1) {
                ddate = ddate + suffix[0];
            } else if(ddate % 10 == 2) {
                ddate = ddate + suffix[1];
            }else {
                ddate = ddate + suffix[2];
            }
            return 'Updated on '+ddate + " "+ month ;
        }
    }
  }
</script>

<style scoped lang="less">
.item {
  padding: 33px 19px;
  border-top: 1px solid rgb(225, 228, 232);
  a {
    font-size: 16px;
    display: block;
    color: rgb(3, 102, 216);
  }
  a:hover {
    text-decoration: underline;
  }
  p {
    font-size: 12px;
  }
  .itemBottom {
    margin-top: 5px;
    p {
      margin-left: 10px;
    }
  }
  .itemBottom>a {
    display: inline;
    font-size: 12px;
    color: rgb(85, 85, 85);
  }
}
</style>
