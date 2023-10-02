<template>
  <main>
    <div class="comeco">
      <Menu />
      <Introduction />
    </div>
    <ModalCookie />
    <Solutions />
    <SaleSimulation />
    <Depoimentos />
    <Cadastro />
    <Footer />
  </main>
</template>

<script>
  import Menu from "../components/navbar/Menu.vue";
  import Introduction from "../components/Introduction.vue";
  import ModalCookie from "../components/ModalCookie.vue";
  import Solutions from "../components/Solutions.vue";
  import SaleSimulation from "../components/SaleSimulation.vue";
  import Depoimentos from "../components/Depoimentos.vue";
  import Cadastro from "../components/Cadastro.vue";
  import TermoUso from "../components/TermoUso.vue";
  import Footer from "../components/NavFooter.vue";
  export default {
    components: {
      Menu,
      Introduction,
      ModalCookie,
      Solutions,
      SaleSimulation,
      Depoimentos,
      Cadastro,
      TermoUso,
      Footer,
    },
  };
</script>
<style scoped>
  main {
    background: url("../assets/background-mobile.svg") no-repeat bottom right;
    height: 90vh;
    background-size: 100vh;
  }

  @media screen and (min-width: 763px) {
    main {
      background: none;
    }
    .comeco {
      background: url("../assets/background-desktop-png.png") no-repeat;
      background-size: 130% 100%;
    }
  }
</style>
