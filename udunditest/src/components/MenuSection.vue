<script setup lang="ts">
import { defineProps } from 'vue';


const props = defineProps({
    isActive: Boolean,
    init: Boolean
});
</script>

<template>
    <div class="menu-section z-[2] relative bottom-56 right-[-585px] ease-in" :class="{ 'open': isActive }">
        <div 
            class="menu-section__title font-bold text-[224px] leading-[289px] text-left text-white w-full overflow-hidden transition-all duration-1000" 
            :class="{ 'init': init, 'w-0' : isActive}">Explore</div>
    </div>
</template>
  
<style>
.menu-section__title {
  font-family: "Didot";
}

.menu-section__title.init {
  width: 0%;
}

@media (max-width: 1199.98px) { 
  .menu-section {
    right: -480px;
  }
  .menu-section__title {
    font-size: 184px;
  }
}

@media (max-width: 991.98px) { 
  .menu-section {
    right: -345px;
  }
  .menu-section__title {
    font-size: 134px;
  }
}

@media (max-width: 767.98px) { 
  .menu-section {
    right: -190px;
  }
  .menu-section__title {
    font-size: 100px;
  }

}

@media (max-width: 750.98px) { 
  .menu-section.open {
    right: 380px;
  }
 }

</style>