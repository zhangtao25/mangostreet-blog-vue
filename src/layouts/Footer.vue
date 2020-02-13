<template>
  <div class="footer">
    <div class="links">
      <a
        href="https://pro.loacg.com/"
        target="_blank"
      >Pro 首页</a>
      <a
        href="https://github.com/sendya/ant-design-pro-vue"
        target="_blank"
      >
        <a-icon type="github" />
      </a>
      <a href="https://ant.design/">Ant Design</a>
      <a href="https://vue.ant.design/">Vue Antd</a>
    </div>
    <div class="copyright">
      Copyright
      <a-icon type="copyright" /> 2020 <span>张温柔</span>
    </div>

    <div style="color: rgba(0, 0, 0, 0.45);margin-top: 10px">
      皖ICP备20002085号
    </div>
  </div>
</template>

<script>
  export default {
    name: 'GlobalFooter',
    data () {
      return {}
    }
  }
</script>

<style>
  .footer{
    padding: 0 16px;
    margin: 48px 0 24px;
    text-align: center;
  }

  .footer .links{
    margin-bottom: 8px;
  }

  .footer .links a{
    color: rgba(0, 0, 0, 0.45);
  }
  .footer .links a:hover{
    color: rgba(0, 0, 0, 0.65);
  }

  .footer .links a:not(:last-child){
    margin-right: 40px;
  }


  .footer .copyright {
    color: rgba(0, 0, 0, 0.45);
    font-size: 14px;
  }
</style>
