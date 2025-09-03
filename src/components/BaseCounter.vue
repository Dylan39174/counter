<template>
  <div class="baseCounter">
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
          class="resetHistory"
          @click="resetCount()">Reset</BaseButton>
      </div>
      <div class="history" v-if="showHistory">

      </div>
  </div>
</template>
  
<script setup lang="ts">

import { ref } from 'vue';
import BaseButton from './BaseButton.vue';
import ShortText from './ShortText.vue';
import vue from '@vitejs/plugin-vue';
import { configDefaults } from 'vitest/config';
import { Icon } from '@iconify/vue';

const count = ref(0);

const showHistory = ref(false);

const increment = () => count.value++;

const decrement = () => count.value >= 1 ? count.value-- : count.value;

const resetCount = () => count.value = 0;


</script>

<style scoped lang="sass">
  @use '../assets/styles/sass/_variables.sass' as var

  .baseCounter
    min-height: 100vh
    display: flex
    justify-content: center
    align-items: center
    background: var.$color-secondary
  
    .counter
      display: flex
      flex-direction: column
      gap: 5vw

    .content
      display: flex
      align-items: center
      gap: 5vw

</style>