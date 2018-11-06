<template>
  <v-app>
    <v-navigation-drawer :mini-variant="miniVariant" :clipped="clipped" v-model="drawer" fixed app>
      <v-list>
        <v-list-tile v-for="(item, i) in items" :to="item.to" :key="i" router exact>
          <v-list-tile-action>
            <v-icon v-html="item.icon" />
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title v-text="item.title" />
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar color="#1867c0" :clipped-left="clipped" fixed app>
      <v-toolbar-side-icon @click="drawer = drawer" class="white--text" />

      <v-menu :nudge-width="100" >
        <v-toolbar-title slot="activator">
          <span class="white--text">{{isAll}}</span>
          <v-icon dark>arrow_drop_down</v-icon>
        </v-toolbar-title>
        <v-list>
          <v-list-tile
            v-for="item in ['全部','原创']"
            :key="item"
          >
            <v-list-tile-title v-text="item" @click="handleIsAll(item)"></v-list-tile-title>
          </v-list-tile>
        </v-list>
      </v-menu>

      <v-menu :nudge-width="100" class="hidden-sm-and-down">
        <v-toolbar-title slot="activator">
          <span class="white--text">时间降序</span>
          <v-icon dark>arrow_drop_down</v-icon>
        </v-toolbar-title>
        <v-list>
          <v-list-tile
            v-for="item in ['时间降序','时间升序','质量降序']"
            :key="item"
          >
            <v-list-tile-title v-text="item"></v-list-tile-title>
          </v-list-tile>
        </v-list>
      </v-menu>

      <v-spacer></v-spacer>
      <v-toolbar-items >
        <v-btn flat class="white--text">推荐</v-btn>
        <v-btn flat class="white--text">面试</v-btn>
        <v-btn flat class="white--text hidden-sm-and-down">vue</v-btn>
        <v-btn flat class="white--text hidden-sm-and-down">react</v-btn>
        <v-btn flat class="white--text hidden-sm-and-down">node</v-btn>
        <v-btn flat class="white--text hidden-sm-and-down">移动端</v-btn>
      </v-toolbar-items>
    </v-toolbar>

    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>

    <v-footer :fixed="fixed" app>
      <span>&copy; 杜延鹏的前端博客</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      isAll:'全部',
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        { icon: 'apps', title: 'Welcome', to: '/' },
        { icon: 'bubble_chart', title: 'Inspire', to: '/inspire' }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Vuetify.js'
    }
  },
  methods:{
    handleIsAll(data){
      this.isAll = data
    }
  }
}
</script>
