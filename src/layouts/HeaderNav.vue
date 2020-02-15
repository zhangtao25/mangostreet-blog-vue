<template>
  <div class="header-nav shadow">
    <div class="margin">
      <div class="left">
        <div class="logo" style="overflow: hidden">
          <img src="https://www.codesheep.cn/css/images/codesheep_logo.png" alt="">
          <span>GentleZhang · 张温柔</span>
<!--          <a-button type="primary" @click="showModal">Open Modal</a-button>-->


          <div class="personal-profile-btn" @click="showModal" style="flex: 1;text-align: right;">
            <img src="https://www.codesheep.cn/css/images/codesheep_logo_heart.jpg" width="40px" alt="">
<!--            <a-icon/>-->
<!--            <a-icon type="down" />-->
            <a-icon type="caret-down" />
          </div>

        </div>


        <a-modal title="Basic Modal" v-model="visible" @ok="handleOk" width="300px" :footer="null" wrapClassName="personal-profile-model">

          <personal-profile/>

        </a-modal>



        <ul class="nav">
          <li v-for="(item,index) of ['首页','关于我']" :key="index" @click="goTo(index)">{{item}}</li>
        </ul>
      </div>
      <div class="right search">
        <a-input-search  placeholder="搜索" style="width: 200px" @search="onSearch" />
      </div>
    </div>

  </div>
</template>
<script>
  import PersonalProfile from './../layouts/PersonalProfile'
  export default {
    components:{
      PersonalProfile
    },
    data(){
      return{
        visible:false
      }
    },
    methods:{
      onSearch(){
        console.log(111)
      },
      goTo(index){
        let obj = {
          '0': '',
          '1': 'about',
          '2': '',
          '3': ''
        }


        let path = obj[index]
        this.$router.push({path:'/' + path})
      },

      showModal() {
        this.visible = true;
      },
      handleOk(e) {
        console.log(e);
        this.visible = false;
      },
    }
  }
</script>

<style>
  .personal-profile-model .ant-modal-body{
    padding: 0;
  }
  .personal-profile-model .ant-modal-header{
    display: none;
  }
  .personal-profile-model .ant-modal-close{
    display: none;
  }
</style>

<style scoped>

  @media screen and (min-width: 1200px) {
    .header-nav .margin{
      display: flex;
      justify-content: space-between;
      padding: 12px 20px;
    }

    .header-nav .left{
      display: flex;
      /*align-items: center;*/
    }


    .header-nav .left > .logo > img{
      width: 40px;
      /*display: block;*/
      margin-left: 15px;
      margin-right: 10px;
    }
    .personal-profile-btn{
      display: none;
    }
  }

  @media screen and (max-width: 1200px) {
    .header-nav .margin{
      display: flex;
      flex-direction: column;
      padding: 12px 12px;
      padding-bottom: 0;
      /*width: 100%;*/
    }

    .header-nav .left{
      display: flex;
      flex-direction: column;
      /*align-items: center;*/
    }

    .header-nav .left > .logo > img{
      width: 40px;
      /*display: block;*/
      /*margin-left: 15px;*/
      margin-right: 10px;
    }
    .nav{
      /*margin-left: 0;*/
      margin-top: 12px !important;
      padding-left: 0;
      border-top: 1px solid rgb(245,246,248);
    }
    .header-nav .right{
      display: none;
    }
  }

  .header-nav{
    background-color: white;
    /*box-shadow: 0 2px 5px 0 rgba(0,0,0,0.16), 0 2px 10px 0 rgba(0,0,0,0.12);*/
  }








  .header-nav .left > .logo{
    display: flex;
    align-items: center;
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
