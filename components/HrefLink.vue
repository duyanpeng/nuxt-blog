<!--  -->
<template>
    <v-card width="80%" :href="href" ripple target="_blank" style="margin-bottom:2px;">
        <v-card-title class="headline">{{title}}</v-card-title>
        <v-card-text>
            <p>{{describe}}</p>
            <div class="text-xs-left">
                <em>
                    <small> {{from}}</small>
                </em>
            </div>
        </v-card-text>
    </v-card>
</template>

<script>
export default {
  props: {
      href:{},
      title:{},
      describe:{},
      from:{}
  },

  data() {
    return {}
  },

  methods: {},

  components: {},

  computed: {},

  mounted() {}
}
</script>
<style scoped>
</style>