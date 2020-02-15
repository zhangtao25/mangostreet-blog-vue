<template>
  <div>
    <div class="container" v-html="html">
      <!--      {{html}}-->
    </div>
  </div>
</template>
<script>
  import marked from 'marked'
  export default {
    data(){
      return{
        html:null
      }
    },
    mounted() {
      let str = `# GentleZhang · 张温柔
*----------------------------------------*
## 关于作者
* 95后，2018年本科毕业于 淮南师范学院 计算机科学与技术专业，现从事IT类工作
* 目前在上海工作，闲时会天花乱坠的写一些自己的项目
* 上海是座大城市，心里是想长期在这里发展的，加油吧~
* 本站是我的个人博客，没事干的时候来更一下
* 爱好：LOL、K歌、旅游、实在太无聊的时候会煲剧



.

## 联系方式
* 微信：zhangtao18158899797
* 微博：芒果街APP
`
      this.html = marked(str)

    }
  }
</script>
