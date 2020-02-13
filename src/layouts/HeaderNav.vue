<template>
  <div class="header-nav shadow">
    <div class="margin">
      <div class="left">
        <div class="logo">
          <img src="https://www.codesheep.cn/css/images/codesheep_logo.png" alt="">
          <span>GentleZhang · 张温柔</span>
        </div>



        <ul class="nav">
          <li v-for="(item,index) of ['首页','归档','公众号','关于我']" :key="index" @click="goTo(index)">{{item}}</li>
        </ul>
      </div>
      <div class="right">
        <a-input-search placeholder="搜索" style="width: 200px" @search="onSearch" />
      </div>
    </div>

  </div>
</template>
<script>
  export default {
    methods:{
      onSearch(){
        console.log(111)
      },
      goTo(index){
        let obj = {
          '0': '',
          '1': 'archives',
          '2': '',
          '3': ''
        }


        let path = obj[index]
        this.$router.push({path:'/' + path})
      }
    }
  }
</script>

<style scoped>

  .header-nav{
    background-color: white;
    /*box-shadow: 0 2px 5px 0 rgba(0,0,0,0.16), 0 2px 10px 0 rgba(0,0,0,0.12);*/
  }
  .header-nav .margin{
    display: flex;
    justify-content: space-between;
    padding: 12px 20px;
  }




  .header-nav .left{
    display: flex;
    /*align-items: center;*/
  }


  .header-nav .left > .logo{
    display: flex;
    align-items: center;
  }
  .header-nav .left > .logo > img{
    width: 40px;
    /*display: block;*/
    margin-left: 15px;
    margin-right: 10px;
  }


  .header-nav .left > .logo > span {
    font-size: 21px;
    display: inline-block;
    vertical-align: top;
    font-weight: 600;
    line-height: 1;
  }


  .nav{
    display: flex;
    list-style: none;
    cursor: pointer;

  }
  .nav li{
    padding: 0 15px;
    font-weight: 300;
    font-size: 16px;
    line-height: 40px;
  }
  .nav li:hover{
    color: #38b7ea;
  }

  .nav li.actived{
    color: #38b7ea;
  }
</style>
