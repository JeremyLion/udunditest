<script setup lang="ts">
import { defineProps, defineEmits } from 'vue';
import PlusBtn from '../assets/images/Plus.svg'

const props = defineProps({
  isActive: Boolean,
  init: Boolean
});

const emits = defineEmits(['activate']);

function emitClick() {
    emits('activate');
}
</script>

<template>
    <div class="button-wrapper right-5 absolute bottom-48 ease-in" :class="{ 'active': isActive }">
      <button class="active-btn text-white flex items-center opacity-100 transition-opacity ease-in font-normal text-2xl" @click="emitClick" :class="{ 'ease-in opacity-0': init }">
        <img class="add mr-5 transition-all delay-200 rounded-full" :class="{'w-8 bg-white' : isActive, 'w-[42px]' : !isActive }" :src="PlusBtn" alt="Button" />
        <span>More Details</span>
      </button>
    </div>
</template>
  
<style scoped>
.active-btn {
  font-family: Lato;
}

@media (max-width: 767.98px) { 
  .button-wrapper {
    right: 0px;
    z-index: 2;
    bottom: 240px;
  }
}

</style>
  