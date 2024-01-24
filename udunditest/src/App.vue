<script setup lang="ts">
import { ref, onMounted } from 'vue';
import Sidebar from './components/Sidebar.vue'
import InfoSection from './components/InfoSection.vue'
import MenuSection from './components/MenuSection.vue'
import ButtonWrapper from './components/ButtonWrapper.vue'
import Facebook from './assets/images/Facebook.svg'
import Instagram from './assets/images/Instagram.svg'

const formOpen = ref(false);
const isActive = ref(false);
const init = ref(true)

const toggleFormOpen = () => {
  formOpen.value = !formOpen.value;
}

onMounted(() => {
  // isActive.value = true;
  setTimeout(() => init.value = false, 1000);
});
</script>

<template>
  <div class="full-screen h-screen w-full flex" id="app">
    <Sidebar :formOpen="formOpen" @toggleFormOpen="toggleFormOpen">
      <template #info>
        <InfoSection :formOpen="formOpen" :isActive="isActive" @closeInfo="toggleFormOpen" />
      </template>

      <template #menuSection>
        <MenuSection :isActive="formOpen" :init="init" />
      </template>

      <template #buttonWrapper>
        <ButtonWrapper :isActive="formOpen" @activate="toggleFormOpen" :init="init" />
      </template>
    </Sidebar>
    <div class="social-media absolute bottom-0 right-8 bottom-10">
      <img class="mb-5" :src="Facebook" alt="">
      <img :src="Instagram" alt="">
    </div>
  </div>
</template>

<style scoped>
.wrapper {
  width: 100%;
  position: relative;
  display: flex;
  align-items: flex-end;
}
.full-screen {
  background-image: url("./assets/images/johannes-plenio-RwHv7LgeC7s-unsplash.jpg");
  display: flex;
  width: 100%;
}

@media (max-width: 767.98px) { 
  .sidebar {
    max-width: 250px;
  }
}

@media (max-width: 750.98px) { 
  .sidebar.open {
    max-width: 100%;
  }

  .sidebar.open .active-btn {
    display: none;
  }
 }

</style>
