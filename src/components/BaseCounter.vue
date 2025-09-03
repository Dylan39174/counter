<template>
  <div class="base-counter">
      <div class='counter'>
        <div class="content">
          <BaseButton
            class="is-big is-icon"
            @click="increment">

            <Icon 
              icon="mdi:plus" 
              width="30" 
              height="30" />
          </BaseButton>
        
          <ShortText class="is-big is-color-white" v-text="count.toString()" />
        
          <BaseButton 
            class="is-big is-icon"
            @click="decrement">

            <Icon 
              icon="mdi:minus" 
              width="30" 
              height="30" />

          </BaseButton>
        </div>
        
        <BaseButton
          class="reset-counter is-big"
          @click="resetCount()">Reset</BaseButton>
      </div>
  </div>
</template>
  
<script setup lang="ts">

import { ref } from 'vue';
import BaseButton from './BaseButton.vue';
import ShortText from './ShortText.vue';
import { Icon } from '@iconify/vue';

const count = ref(0);

const increment = () => count.value++;

const decrement = () => count.value >= 1 ? count.value-- : count.value;

const resetCount = () => count.value = 0;

</script>

<style scoped lang="sass">
  @use '../assets/styles/sass/_variables.sass' as var

  .base-counter
    display: flex
    justify-content: center
    align-items: center
    background: var.$color-secondary
    flex: 1
  
    .counter
      display: flex
      flex-direction: column
      gap: 5vw

    .content
      display: flex
      align-items: center
      gap: 5vw

    .reset-counter
      margin: auto

</style>