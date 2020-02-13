<template>
  <div id="app">
<!--    <a-button type="primary">按钮</a-button>-->
<!--    <div class="margin test"></div>-->
    <header-nav/>
<!--    <router-view/>-->


    <div class="margin">
      <a-row class="container">
        <a-col :span="5">
          <personal-profile/>
        </a-col>
        <a-col :span="14">
          <div class="shadow" style="margin: 0 20px;padding:15px;background-color: white;border-radius: 10px">
            <router-view/>
          </div>

        </a-col>

        <a-col :span="5">
          <template>
            <a-card hoverable style="width: 240px">
              <img
                alt="example"
                src="https://os.alipayobjects.com/rmsportal/QBnOOoLaAfKPirc.png"
                slot="cover"
              />
              <a-card-meta title="Europe Street beat">
                <template slot="description"
                >www.instagram.com</template
                >
              </a-card-meta>
            </a-card>
          </template>
        </a-col>
      </a-row>
    </div>

    <app-footer/>

  </div>
</template>

<script>
  import HeaderNav from './layouts/HeaderNav'
  import PersonalProfile from './layouts/PersonalProfile'
  import Footer from './layouts/Footer'
  export default {
    components:{
      HeaderNav,
      PersonalProfile,
      "AppFooter": Footer
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

  .margin {
    max-width: 1800px;
    min-width: 1200px;
    margin: 0 auto;
    padding: 0 20px;
    /*box-sizing: border-box;*/
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
</style>
