<script setup lang="ts">
import { ref, onMounted } from 'vue';
import PlusBtn from './assets/images/Plus.svg'
import closeBtn from './assets/images/close.svg'

const formOpen = ref(false);
const isActive = ref(false);

onMounted(() => {
  isActive.value = true;
  setTimeout(() => {
    isActive.value = false;
  }, 1000);
});
</script>

<template>
  <div class="full-screen h-screen w-full flex" id="app">
    <div class="wrapper">
      <div class="sidebar" :class="{'open': formOpen}">
        <div class="panel" :class="{'open': formOpen}"></div>
        <div class="wrap">
          <div class="info" :class="{'open': formOpen}">
            <div class="info__wrapper">
              <div class="info__close w-full flex justify-end items-end px-6 pt-6">
                <button @click="formOpen = false"><img :src="closeBtn" /></button>
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
          <div class="menu-section" :class="{'open': formOpen}">
            <div class="menu-section__title" :class="{ 'init': isActive }">Explore</div>
          </div>
          <div class="button-wrapper">
            <div class="active-btn" :class="{ 'init': isActive }">
              <img class="add" :class="{'open': formOpen}" @click="formOpen = true" :src="PlusBtn" />
              More Details
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.button-wrapper {
  border-radius: 50px;
  transition: 0.5s;
  position: absolute;
  right: 40px;
  bottom: 180px;
}

.info {
  height: 43px;
  width: 43px;
  background: #fff;
  border-radius: 50px;
  transition: 0.5s;
  position: absolute;
  left: 165px;
  top: 75%;
  opacity: 0;
  overflow: hidden;
}
.info.open {
  border-radius: 0;
  clip-path: none;
  height: 690px;
  width: 580px;
  left: 120px;
  top: 50%;
  transform: translate(0, -50%);
  opacity: 1;
  z-index: 3;
}

.info .info__wrapper {
  position: relative;
  right: 40px;
  opacity: 0;
  transition: 0.5s;
  transition-delay: 0.5s;
}

.info.open .info__wrapper {
  right: 0px;
  opacity: 1;
}

.info__title {
  font-family: "Didot";
  color: #611818;
}

.info__readmore {
  background-image: radial-gradient(at center bottom, rgba(97, 24, 24, 1), rgba(163, 103, 84, 1));
  font-family: "Lato";
}

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

.sidebar {
  background: #611818;
  width: 100%;
  max-width: 410px;
  height: 100vh;
  position: relative;
  z-index: 1;
  display: flex;
  justify-content: flex-end;
  align-items: flex-end;
  transition: 1s;
}

.panel {
  height: 100vh;
  width: 120px;
  background: #3b1010;
  position: absolute;
  left: -120px;
  transition: 1s;
}

.panel.open {
  left: 0;
}

.menu-section {
  z-index: 2;
  position: relative;
  bottom: 222px;
  right: -585px;
  transition: 1s;
}

.menu-section__title {
  font-family: "Didot";
  font-size: 224px;
  font-weight: 700;
  line-height: 289px;
  letter-spacing: 0px;
  text-align: left;
  color: #fff;
  width: 100%;
  transition: 1s;
  overflow: hidden;
}

.menu-section.open .menu-section__title {
  width: 0%;
}


.menu-section__title.init {
  width: 0%;
}

.active-btn.init{
  opacity: 0;
}

.active-btn {
  font-family: Lato;
  font-size: 25px;
  font-weight: 400;
  line-height: 30px;
  color: #fff;
  display: flex;
  align-items: center;
  transition: 1s;
  opacity: 1;
}

.add {
  margin-right: 20px;
  transition: 1s;
  border-radius: 50px;
  opacity: 1;
  width: 42px;
}

.add.open {
  background: #fff;
  width: 32px;
  opacity: 0;
}

.add-product {
  transition: all 2s ease;
  cursor: pointer;
}

.add-product.open {
  background-color: #FAFAFA;
  padding: 18px 32px;
  border-radius: 5px;
  width: 420px;
  height: 398px;
  cursor: default;
}

@media (max-width: 1399.98px) { 
  
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
  .sidebar {
    max-width: 250px;
  }
  .menu-section {
    right: -190px;
  }
  .menu-section__title {
    font-size: 100px;
  }

  .button-wrapper {
    right: -10px;
    z-index: 2;
    bottom: 240px;
  }
}

@media (max-width: 750.98px) { 
  .sidebar.open {
    max-width: 100%;
  }

  .menu-section.open {
    right: 380px;
  }

  .sidebar.open .active-btn {
    display: none;
  }

  .info.open {
    left: 0;
    width: 100%;
    height: 750px;
  }
 }

</style>
