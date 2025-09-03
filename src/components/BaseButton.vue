<template>
  <button :class="[props.class, 'button']">
    <slot></slot>
  </button>
</template>

<script setup lang="ts">
import { defineProps } from 'vue';
import type { ButtonType } from '../types/ButtonType';

const props = defineProps<ButtonType>();
</script>

<style scoped lang="sass">
  @use '../assets/styles/sass/_variables' as var

  .button
    cursor: pointer
    padding: 5px 10px
    width: fit-content
    display: flex
    justify-content: center
    align-items: center
    background-color: var.$color-primary
    color: var.$color-light
    box-shadow: 2px 2px 3px rgba(var.$color-dark, .5)
    border-radius: 10px
    text-transform: uppercase
    font-size: 1rem
    letter-spacing: .05em
    transition: box-shadow .2s ease-in-out

    &:hover
      box-shadow: none

    &.is-big
      padding: max(25px, 2.5vw)

    &.is-icon
      width: 100px
      height: 100px

</style>