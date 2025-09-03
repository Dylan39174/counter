<template>
  <div class='counter-box'>
    <BaseCounter />
    <CounterHistory :class="{'is-opened': showHistory }" />
    <BaseButton class="show-history" @click="showHistory = !showHistory">{{ getToggleHistoryLabel() }}</BaseButton>
  </div>
</template>

<script setup lang="ts">
    import BaseCounter from './BaseCounter.vue';
    import CounterHistory from './CounterHistory.vue';
    import BaseButton from './BaseButton.vue';
    import { ref } from 'vue';

    const showHistory = ref(false);

    const getToggleHistoryLabel = () => showHistory.value ? "Masquer l'historique" : "Afficher l'historique";
</script>

<style scoped lang="sass">
    .counter-box
        height: 100vh
        display: flex
        flex-direction: column  

    .show-history
        position: absolute
        bottom: 15px
        right: 15px
</style>