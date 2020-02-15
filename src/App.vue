<template>
  <div id="app">
    <a-back-top />
<!--    <a-button type="primary">按钮</a-button>-->
<!--    <div class="margin test"></div>-->
    <header-nav/>
<!--    <router-view/>-->


    <div class="margin">
<!--      <p>三生三世{{clientWidth}}</p>-->
      <a-row class="container" v-if="clientWidth>1200">
        <a-col :span="5">
          <personal-profile/>
        </a-col>
        <a-col :span="14">
          <div class="shadow router-view-wrap">
            <router-view/>
          </div>
        </a-col>
        <a-col :span="5">
          <sidebar></sidebar>
        </a-col>
      </a-row>

      <a-row class="container" v-if="clientWidth<1200 || clientWidth == 1200">
        <a-col :span="24">
          <div class="shadow router-view-wrap_1200">
            <router-view/>
          </div>
        </a-col>
        <a-col :span="24" style="padding-top: 40px">
          <sidebar></sidebar>
        </a-col>
      </a-row>
    </div>
    <app-footer/>
  </div>
</template>

<script>
  import HeaderNav from './layouts/HeaderNav'
  import PersonalProfile from './layouts/PersonalProfile'
  import Sidebar from './layouts/Sidebar'
  import Footer from './layouts/Footer'
  export default {
    components:{
      HeaderNav,
      PersonalProfile,
      Sidebar,
      "AppFooter": Footer
    },
    data(){
      return{
        clientWidth: `${document.documentElement.clientWidth}`,
        timer:false
      }
    },
    created() {
      this.fn(document.documentElement.clientWidth);
    },
    mounted() {
      const _this = this;
      window.onresize = () => {
        return (() => {
          _this.clientWidth = `${document.documentElement.clientWidth}`;
        })();
      }
    },
    methods:{
      fn(){
        console.log(111111)
      }
    },
    watch: {
      clientWidth (val) {
        if(!this.timer) {
          this.clientWidth = val
          this.timer = true
          let _this = this
          setTimeout(function () {
            _this.timer = false
          }, 500)
        }
        this.fn(val);
      }
    }
  }
</script>

<style>

  /*#app > .margin {*/
  /*  max-width: 1800px;*/
  /*  min-width: 1200px;*/
  /*  margin: 0 auto;*/
  /*  padding: 0 20px;*/
  /*  !*box-sizing: border-box;*!*/
  /*}*/

  /*全局的样式*/

  .shadow{
    border-color: rgba(0, 0, 0, 0.09);
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.09);
  }


  @media screen and (min-width: 1200px) {
    .margin {
      max-width: 1800px;
      min-width: 1200px;
      margin: 0 auto;
      padding: 0 20px;
      /*box-sizing: border-box;*/
    }



  }




  @media screen and (max-width: 1200px) {
    .margin{
      margin: 0 auto;
      padding: 0 20px;
    }

    #app > .margin {
      margin: 0;
      padding: 0;
    }
  }


  body{
    background-color: rgb(246,248,249) !important;
    /*background-color: rebeccapurple !important;*/
  }


  #app > .margin > .container{
    margin-top: 40px;
  }

  /*.test{*/
  /*  height: 100px;*/
  /*  border: 1px solid salmon;*/
  /*}*/

  #app ol, #app ul,#app dl {
    margin-top: 0;
    margin-bottom: 0;
  }


  .router-view-wrap{
    margin: 0 20px;
    padding:15px;
    background-color: white;
    border-radius: 10px;
  }
  .router-view-wrap_1200{
    margin: 0 0px;
    padding:0px;
    background-color: white;
    border-radius: 10px;
  }
</style>
