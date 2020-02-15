<template>
  <a-card class="shadow" hoverable style="border-radius: 10px;border: none">
<!--    <img-->
<!--      alt="example"-->
<!--      src="https://gw.alipayobjects.com/zos/rmsportal/JiqGstEfoWAOHiTxclqi.png"-->
<!--      slot="cover"-->
<!--    />-->
    <div slot="cover" style="display: flex;padding: 15px 10px">
      <img src="https://www.codesheep.cn/css/images/codesheep_logo_heart.jpg" style="width: 40%;height: 40%" alt="">
      <ul style="list-style: none;color: #808080ad;line-height: 2;padding-left:10%">
        <li>昨夜雨疏风骤，</li>
        <li>浓睡不消残酒。</li>
        <li>试问卷帘人，</li>
        <li>却道海棠依旧。</li>
        <li>知否，知否？</li>
        <li>应是绿肥红瘦。</li>
      </ul>
    </div>
    <template class="ant-card-actions" slot="actions">
<!--      <a-icon type="setting" />-->
<!--      <a-icon type="edit" />-->
<!--      <a-icon type="ellipsis" />-->
<!--      <a-icon type="setting" />-->
<!--      <a-icon type="edit" />-->
<!--      <a-icon type="ellipsis" />-->



      <svg class="icon" aria-hidden="true">
        <use xlink:href="#iconweixin"></use>
      </svg>

      <svg class="icon" aria-hidden="true">
        <use xlink:href="#iconQQ"></use>
      </svg>



      <a href="https://weibo.com/u/5501958344" target="_blank">
        <svg class="icon" aria-hidden="true">
          <use xlink:href="#iconweibo"></use>
        </svg>
      </a>


      <a href="https://github.com/zhangtao25" target="_blank">
        <svg class="icon" aria-hidden="true">
          <use xlink:href="#iconGitHub"></use>
        </svg>
      </a>



    </template>
    <a-card-meta title="张温柔" style="border-top:1px solid #eeeeee;padding-top:20px">
<!--      description="Huster & Developer"-->




      <div slot="description">

        <a-col :span="15">
          <p>Huster & Developer</p>
          <p><a-icon type="environment"/>上海</p>
        </a-col>

        <a-col :span="9">
          <a-button type="primary">关注我</a-button>
        </a-col>





      </div>
      <a-avatar
        slot="avatar"
        src="/touxiang.jpg"
      />
    </a-card-meta>
  </a-card>
</template>
