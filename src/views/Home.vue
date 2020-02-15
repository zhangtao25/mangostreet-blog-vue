<template>
  <a-list itemLayout="vertical" size="large" :pagination="pagination" :dataSource="listData">
    <div slot="footer"><b>ant design vue</b> footer part</div>
    <a-list-item slot="renderItem" slot-scope="item, index" key="item.title">
<!--      <template slot="actions" v-for="{type, text} in actions">-->
<!--        <span :key="type">-->
<!--          <a-icon :type="type" style="margin-right: 8px" />-->
<!--          {{text}}-->
<!--        </span>-->
<!--      </template>-->
      <img
        slot="extra"
        height="100"
        alt="logo"
        src="https://gw.alipayobjects.com/zos/rmsportal/mqaQswcyDLcXyDKnZfES.png"
      />
      <a-list-item-meta :description="item.description">
        <a slot="title" :href="item.href">{{item.title}}</a>
<!--        <a-avatar slot="avatar" :src="item.avatar" />-->
      </a-list-item-meta>
      {{item.content}}
    </a-list-item>
  </a-list>
</template>
<script>
  const listData = [];
  for (let i = 0; i < 23; i++) {
    listData.push({
      href: 'https://www.antdv.com/',
      title: `封装一个流水号ID生成器：id-spring-boot-starter ${i}`,
      avatar: 'https://zos.alipayobjects.com/rmsportal/ODTLcjxAfvqbxHnVXCYX.png',
      description:
        '别再用数据库自增ID，UUID了，用流水号生成器生成吧',
      content:
        '',
    });
  }

  export default {
    data() {
      return {
        listData,
        pagination: {
          onChange: page => {
            console.log(page);
          },
          pageSize: 3,
        },
        actions: [
          // { type: 'star-o', text: '156' },
          // { type: 'like-o', text: '156' },
          // { type: 'message', text: '2' },
        ],
      };
    },
  };
</script>
<style></style>
