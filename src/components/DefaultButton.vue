<script setup lang="ts">
import { computed } from 'vue'

const props = defineProps({
  label: {
    type: String,
    default: ''
  },
  variant: {
    type: String,
    default: ''
  },
  borderRadius: {
    type: Number,
    default: 12
  },
  padding: {
    type: Number,
    default: 16
  },
  iconeInicio: {
    type: Object,
    default: null
  },
  vertical: {
    default: false,
    type: Boolean
  },
  disabled: {
    type: Boolean,
    default: false
  }
})

const emits = defineEmits(['click'])

const variantButton = computed(() => {
  return props.variant ? `el-button-${props.variant}` : ''
})

const verticalButton = computed(() => {
  return props.vertical ? 'button-vertical' : ''
})

const disabledButton = computed(() => {
  return props.disabled ? 'disabled' : ''
})

function checkClick(e: Event) {
  e.preventDefault()
  if (!props.disabled) emits('click', e)
}
</script>

<template>
  <div class="button-container">
    <el-button
      :icon="iconeInicio"
      :class="[variantButton, verticalButton, disabledButton]"
      :border-radius="borderRadius"
      :padding="padding"
      @click="checkClick"
      >{{ label }}</el-button
    >
  </div>
</template>

<style lang="less">
.button-container {
  width: 100%;

  .el-button {
    color: #1a4170;
    width: 100%;
  }

  // .el-button:hover {
  //   background-color: var(--hover-grey);
  //   box-shadow: 4px 4px 8px var(--hover-shadow);
  //   border-color: var(--hover-grey);
  // }

  .el-button-blue {
    background-color: #1a4170;
    border-color: #1a4170;
    color: white;
  }

  .el-button-blue:hover {
    background-color: var(--hover-blue);
    border-color: #1a4170;
  }

  // .el-button-accept {
  //   color: var(--medium-blue);

  //   .el-icon {
  //     color: var(--green);
  //   }
  // }

  // .el-button-accept:hover {
  //   border-color: var(--medium-blue);
  //   background-color: white;
  //   box-shadow: none;
  // }
}
</style>
