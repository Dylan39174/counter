<template>
  <div class='counter-history'>
    
  </div>
</template>

<script setup lang="ts">

</script>

<style scoped lang="sass">
    @use '../assets/styles/sass/_variables.sass' as var

    .counter-history
        background-color: var.$color-dark
        transition: flex .5s ease-out

        &:not(.is-opened)
            flex: 0

        &.is-opened
            flex: 1

</style>