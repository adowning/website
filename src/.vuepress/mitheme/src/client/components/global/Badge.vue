<script setup lang="ts">
defineProps({
  type: {
    type: String,
    required: false,
    default: 'tip',
  },
  text: {
    type: String,
    required: false,
    default: '',
  },
  vertical: {
    type: String,
    required: false,
    default: undefined,
  },
})
</script>

<template>
  <span
    class="badge"
    :class="type"
    :style="{
      verticalAlign: vertical,
    }"
  >
    <slot>{{ text }}</slot>
  </span>
</template>

<style lang="scss">
.badge {
  display: inline-block;
  font-size: 14px;
  height: 18px;
  line-height: 18px;
  border-radius: 3px;
  padding: 0 6px;
  color: var(--c-bg);
  vertical-align: top;
  transition: color var(--t-color), background-color var(--t-color);

  &.tip {
    background-color: var(--c-badge-tip);
  }

  &.warning {
    background-color: var(--c-badge-warning);
  }

  &.danger {
    background-color: var(--c-badge-danger);
  }

  .table-of-contents & {
    vertical-align: middle;
  }

  & + & {
    margin-left: 5px;
  }
}
</style>
