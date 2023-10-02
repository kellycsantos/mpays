<template>
  <div id="main">
    <div class="init">
      <h1>
        Tecnologia e segurança pra você <span class="bold">vender mais.</span>
      </h1>
      <p>
        Venda online com a segurança e tecnologia mpays. Soluções simples e
        flexíveis para digitalizar o seu negócio.
      </p>
    </div>

    <div class="img-container">
      <img src="../components/assets/pixelbookgo.svg" />
    </div>
  </div>
</template>
<style scoped>
  #main {
    color: #fff;
    padding-inline: 32px;
    max-width: 100vw;
    height: max-content;
    margin-bottom: 80px;
    overflow-x: hidden;
  }

  h1 {
    font-weight: 400;
    margin-bottom: 20px;
  }

  .init > h1,
  .init > p {
    width: clamp(265px, 30vw, 438px);
  }
  .img-container {
    position: relative;
    left: 0 !important;
    max-width: 100vw !important;
    overflow-x: visible;
  }

  img {
    width: clamp(382px, 45vw, 763px);
    margin-left: -10%;
  }

  @media screen and (min-width: 768px) {
    #main {
      display: flex;
      align-items: center;
      height: 75vh;
      overflow: hidden;
    }

    .img-container {
      margin-left: 120px;
      max-width: 500px;
      margin-bottom: -180px;
    }
    h1 {
      font-weight: 400;
      margin-bottom: 20px;
      font-size: 49px;
      width: 455.32px;
    }
    .init {
      margin-bottom: 150px;
    }
  }
</style>
