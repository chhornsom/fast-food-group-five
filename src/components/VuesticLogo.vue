<template>
  <img src="https://i.pinimg.com/564x/b6/82/8c/b6828cfed81f1af361a63681d04e0888.jpg" alt="" />
</template>
<script lang="ts" setup>
import { computed } from 'vue'
import { useColors } from 'Vuestic-ui'

const { getColor } = useColors()

const props = withDefaults(
  defineProps<{
    height?: number
    start?: string
    end?: string
  }>(),
  {
    height: 18,
    start: 'primary',
    end: undefined,
  },
)

const colorsComputed = computed(() => {
  return {
    start: getColor(props.start),
    end: getColor(props.end || props.start),
  }
})
</script>
<style>
img {
  border-radius: 50%;
  width: 50px;
  height: 50px;
}
</style>
