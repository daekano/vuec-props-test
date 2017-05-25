<template>
  <div class="prop-test">
    {{ a }}
    {{ b }}
    {{ c }}
    {{ computedScope }}
    {{ methodScope() }}
  </div>
</template>

<script>
/*eslint-disable*/
export default {
  data() {
    return {};
  },
  beforeCreate() {
    console.log(this._uid, 'beforeCreate hook', this.$options.propsData.a, this.$options.propsData.b, this.$options.propsData.c);
  },
  created() {
    console.log(this._uid, 'created hook', this.a, this.b, this.c);
  },
  mounted() {
    console.log(this._uid, 'mounted hook', this.a, this.b, this.c);
  },
  props: {
    a: {
      type: String,
    },
    b: {
      type: Number,
    },
    c: {
      type: Boolean,
      default: false,
    },
  },
  computed: {
    computedScope() {
      console.log(this._uid, 'computed property', this.a, this.b, this.c);
    },
  },
  methods: {
    methodScope() {
      console.log(this._uid, 'method', this.a, this.b, this.c);
    },
  },
};
</script>

<style>
</style>