<template>
  <div class="wrapper">
    <div class="main-contents">

    </div>
  </div>
</template>

<script>

export default {
  props: {
    isActive: {
      type: Number,
      default: 1
    }
  },

  components: {
  },

  data() {
    return {
    };
  },
  methods: {
    tabChange(num) {
      this.isActive = num;
    }
  },
  created: function() {}
};
</script>