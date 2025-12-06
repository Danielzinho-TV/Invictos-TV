<template>
  <div class="item-content">
    <div>
      <h3 class="item-title"> Futebol </h3>
      <span class="item-description"> O melhor do futebol nacional e internacional</span>
    </div>
    <div class="item-images">
      <div class="item-card">
        <img class="item-image" src="@/assets/brasileirao-premiere.webp" />
      </div>
      <div class="item-card">
        <img class="item-image" src="@/assets/champions-league.webp" />
      </div>
    </div>
  </div>
  <div class="item-content">
    <div>
      <h3 class="item-title"> Filmes e séries </h3>
      <span class="item-description"> Os lançamentos do cinema, da TV e do streaming</span>
    </div>
    <div class="item-images">
      <div class="item-card">
        <img class="item-image" src="@/assets/stranger-things.webp" />
      </div>
      <div class="item-card">
        <img class="item-image" src="@/assets/avengers-endgame.webp" />
      </div>
    </div>
  </div>
  <div class="item-content">
    <div>
      <h3 class="item-title"> TV </h3>
      <span class="item-description"> Todos os canais abertos e fechados</span>
    </div>
    <div class="item-images">
      <div class="item-card">
        <img class="item-image" src="@/assets/tv-aberta.webp" />
      </div>
      <div class="item-card">
        <img class="item-image" src="@/assets/canais-fechados.webp" />
      </div>
    </div>
  </div>
  <div class="item-content">
    <div>
      <h3 class="item-title"> Reality Show </h3>
      <span class="item-description"> Câmeras ao vivo dos melhores realities do país </span>
    </div>
    <div class="item-images">
      <div class="item-card">
        <img class="item-image" src="@/assets/bbb.webp" />
      </div>
      <div class="item-card">
        <img class="item-image" src="@/assets/fazenda.webp" />
      </div>
    </div>
  </div>
</template>

<script setup>

</script>

<style lang="scss" scoped>

.item-content{
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.item-title{
  color: #FFFFFF;
  font-size: 24px;
  font-weight: 700;
}

.item-description {
  color: rgba(255,255,255,0.7);
  font-size: 16px;
  font-weight: 500;
}

.item-images{
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 8px;
  @media(min-width: 576px) {
    justify-content: center;
    flex-direction: row;
    gap: 16px;
  }
}

.item-card {
  width: 220px;
  height: 220px;
  border: 1px solid rgba(255,255,255,0.7);
}

.item-image{
  width: 100%;
  height: 100%;
}
</style>

