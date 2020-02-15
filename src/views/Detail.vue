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
      this.html = marked('# Marked in browser\n\nRendered by **marked**.')

    }
  }
</script>
