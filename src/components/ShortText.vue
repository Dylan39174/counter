<template>
  <component :is="props.tag" :class="[props.class, 'shortText']">
    <slot></slot>
  </component>
</template>

<script setup lang="ts">
import { defineProps, withDefaults } from 'vue';
import type { ShortTextType } from '../types/ShortTextType';

const props = withDefaults(defineProps<ShortTextType>(), {
    class: '',
    tag: 'span',
});
</script>

<style scoped lang="sass">
  @use '../assets/styles/sass/_variables.sass' as var

  .shortText
    &.is-color-white
      color: var.$color-light

    &.is-big
      font-size: 4rem

</style>