<template>
  <div class="image-container">
    <div class="overlay">
      <div class="text-center">
        <h1 class="text-white">KNJIŽNICA</h1>
        <h5 class="text-white">
          WEB knjižnica uz mogućnost prijave, pretraživanja i rezerviranja
          knjiga.
        </h5>
        <div class="button-container"></div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.image-container {
  position: relative;
  height: 100vh;
  background-image: url("/images/frontpage.jpeg");
  background-size: cover;
  background-position: center;
}

.overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.button-container {
  margin-top: 20px;
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  justify-content: center;
}
</style>
