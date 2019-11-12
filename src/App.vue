<template>
  <div class="online-view">
    <slot v-if="online"></slot>
    <slot v-else name="offline"></slot>
  </div>
</template>

<script lang="ts">
export default {
  data() {
    return {
      online: navigator.onLine
    };
  },
  mounted() {
    window.addEventListener("online", this.onchange);
    window.addEventListener("offline", this.onchange);
    this.onchange();
  },
  beforeDestroy() {
    window.removeEventListener("online", this.onchange);
    window.removeEventListener("offline", this.onchange);
  },
  methods: {
    onchange() {
      this.online = navigator.onLine;
      this.$emit(this.online ? "online" : "offline");
    }
  }
};
</script>
