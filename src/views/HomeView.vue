<template>
  <div class="home-container">
     <div class="home-content">
      <div class="home-presentation">
        <h1 class="home-title"> Assine o IPTV da Invictos e tenha o melhor da TV e dos streamings</h1>
        <button  @click="sendMessage" class="test-button" ref="mainButton"> Solicitar teste grátis </button>
      </div>

      <span class="home-description"> Cansado de ter que assinar dezenas de streamings para assistir sua série/filme favorito ou não conseguir assistir o jogo do time do seu coração? assine o IPTV da Invictos e tenha tudo isso e muito mais por um preço extremamente baixo!</span>
      <IPTVContent />
     </div>

      <button
      v-if="showFloatingButton"
      class="floating-button"
      @click="sendMessage"
    >
      Solicitar teste grátis
    </button>

  </div>
</template>

<script setup>
import IPTVContent from '../components/IPTVContent.vue';
import { ref, onMounted, onUnmounted } from 'vue';

const phone = '5583994098461';
const message = 'Olá, Daniel! Gostaria de solicitar um teste grátis do IPTV.';

const sendMessage = () => {
  const encoded = encodeURIComponent(message);
  const url = `https://wa.me/${phone}?text=${encoded}`;
  window.open(url, '_blank');
};

const showFloatingButton = ref(false);
const mainButton = ref(null);

let observer;

onMounted(() => {
  observer = new IntersectionObserver(
    (entries) => {
      const entry = entries[0];
      showFloatingButton.value = !entry.isIntersecting;
    },
    { threshold: 0 }
  );

  if (mainButton.value) {
    observer.observe(mainButton.value);
  }
});

onUnmounted(() => {
  if (observer && mainButton.value) {
    observer.unobserve(mainButton.value);
  }
});
</script>



<style lang="scss" scoped>
.home-container{
  background: #000000;
  display: flex;
  justify-content: center;
}

.home-content{
  width: 100vw;
  display: flex;
  flex-direction: column;
  max-width: 760px;
  padding: 16px;
  gap: 24px;
}

.home-presentation{
  width: 100%;
  max-width: 1200px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 16px;
}

.home-title{
  color: rgb(229, 9, 20);
  font-family: unset;
  font-size: 32px;
  font-weight: 700;
  text-align: center;
}

.test-button,
.floating-button {
  height: 40px;
  font-size: 16px;
  font-weight: 500;
  color: #FFFFFF;
  background-color: rgb(229, 9, 20);
  border: 1px solid rgb(180, 2, 11);
  border-radius: 8px;
  width: 220px;
  cursor: pointer;

  &:hover{
    background-color: rgb(189, 11, 20);
  }
}

.floating-button {
  position: fixed;
  bottom: 16px;
  left: 50%;
  transform: translateX(-50%);
  z-index: 999;
  box-shadow: 0px 4px 16px rgba(0,0,0,0.2);
}

.home-description{
  color: rgba(255,255,255,0.7);
  font-size: 16px;
  font-weight: 500;
}
</style>
