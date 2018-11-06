<template>
  <v-layout column justify-center align-center>
    <!-- <v-flex
      xs12
      sm8
      md6> -->

    <href-link v-for="item in dataList" :key="item.id" :href="item.href" :describe="item.describe" :title="item.title" :from="item.from"></href-link>
    <!-- <v-flex xs12> -->
          <v-card width="80%">
            <v-card-text width="100%" style="text-align:center;">
              <v-pagination
                color="#1867c0"
                v-model="page"
                :length="5"
              ></v-pagination>
            </v-card-text>
          </v-card>
        <!-- </v-flex> -->
    <!-- </v-flex> -->
  </v-layout>
</template>

<script>
import HrefLink from '~/components/HrefLink.vue'

export default {
  data() {
    return {
      page: 1,
      dataList: [
        {
          id: 1,
          href: 'https://juejin.im/post/5ac26089f265da23970709aa',
          title: 'js数组简单算法面试速记',
          describe: '排序，去重，斐波那契数列，深拷贝',
          from: '原创'
        },
        {
          id: 2,
          href: 'https://juejin.im/post/5ac84501f265da2391485d38',
          title: 'js获取元素位置方法总结',
          describe: 'js获取元素位置方法总结',
          from: '原创'
        },
        {
          id: 3,
          href: 'https://juejin.im/post/5ac249f76fb9a028cb2dccb9',
          title: 'js继承面试速记(内容抄自高程三)',
          describe: 'js继承面试速记(内容抄自高程三)',
          from: '原创'
        },
        {
          id: 4,
          href: 'https://juejin.im/post/5be01548e51d4557dd6f09bb',
          title: 'css实现垂直水平居中',
          describe: 'css实现垂直水平居中',
          from: '原创'
        },
        {
          id: 5,
          href: 'https://juejin.im/post/5be0159b6fb9a049ee7fe7f1',
          title: 'css形变及动画',
          describe: 'css形变及动画',
          from: '原创'
        },
        {
          id: 6,
          href: 'https://juejin.im/post/5be015efe51d450b951e2d6e',
          title: 'js数组、字符串方法',
          describe: 'js数组、字符串方法',
          from: '原创'
        }
      ]
    }
  },
  components: {
    HrefLink
  }
}
</script>
