<script setup lang="ts">
import { defineProps, defineEmits } from 'vue';
import closeBtn from '../assets/images/close.svg'

const props = defineProps({
  formOpen: Boolean,
  isActive: Boolean
});

const emits = defineEmits(['closeInfo']);

function closeInfo() {
  emits('closeInfo');
}
</script>

<template>
  <div class="info bg-white overflow-hidden absolute transition-all duration-500" 
  :class="{'left-[120px] w-[580px] top-1/2 opacity-100 z-[3] h-[690px] rounded-none open transform -translate-y-1/2': formOpen, 'h-[43px] w-[43px] left-[165px] top-3/4 opacity-0 rounded-full' : !formOpen}">
    <!-- Info section content -->
    <div class="info__wrapper relative transition-all duration-500 delay-500" :class="{ 'right-0 opacity-100' : formOpen, 'opacity-0 right-[10px]' : !formOpen}">
      <div class="info__close w-full flex justify-end items-end px-6 pt-6">
        <button @click="closeInfo"><img :src="closeBtn" /></button>
      </div>
      <div class="info__title text-[66px] px-16 font-bold">Explore</div>
      <div class="info__body px-16 pt-4 pb-8 text-lg font-normal leading-[26px] text-gray-900">
        Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt. Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit, sed quia non numquam eius modi tempora incidunt ut labore et dolore magnam aliquam quaerat voluptatem. Ut enim ad minima veniam, quis nostrum exercitationem ullam corporis suscipit laboriosam, nisi ut aliquid ex ea commodi consequatur? 
      </div>
      <div class="info__readmore w-[255px] ml-16 text-white p-[13px] font-normal text-lg uppercase text-center">
        Read More
      </div>
    </div>
  </div>
</template>


<style scoped>
.info__title {
  font-family: "Didot";
  color: #611818;
}

.info__readmore {
  background-image: radial-gradient(at center bottom, rgba(97, 24, 24, 1), rgba(163, 103, 84, 1));
  font-family: "Lato";
}

@media (max-width: 750.98px) { 
  .info.open {
    left: 0;
    width: 100%;
    height: 750px;
  }
 }
</style>