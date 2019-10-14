<template>
  <button class="button" :class="classNames" @click="onClick">
    <slot></slot>
  </button>
</template>

<script lang="ts">
import Vue from "vue";
export default Vue.extend({
  name: "my-button",
  props: {
    isPrimary: {
      type: Boolean,
      dafault: false
    }
  },
  computed: {
    classNames(): string[] {
      return this.isPrimary ? ["is-primary"] : [];
    }
  },
  methods: {
    onClick() {
      this.$emit("click");
    }
  }
});
</script>

<style>
button {
  border: 1px solid #eee;
  border-radius: 3px;
  background-color: #ffffff;
  cursor: pointer;
  font-size: 15pt;
  padding: 3px 10px;
  margin: 10px;
}

.is-primary {
  background: blue;
}
</style>
