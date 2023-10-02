<template>
  <div id="depoimentos">
    <h2>Depoimentos</h2>
    <p class="subtitle">O suporte ao cliente é nossa primeira prioridade.</p>


    <div  :class="isDesktop ? 'card-row' : ''">
    <div
      class="card-depoimento"
     
      v-for="(depoimento, index) in depoimentos"
      :key="index"
      v-show="index == active || isDesktop"
    >
      <div class="card-image">
        <img :src="`/assets/depoimentos/${depoimento.image}.svg`" />
      </div>
      <img class="quote-icon" src="/assets/depoimentos/quote-icon.svg" />
      <p>
        {{ depoimento.descricao }}
      </p>
      <h4>{{ depoimento.cliente }}</h4>
      <h5>{{ depoimento.cargo }}</h5>
    </div>
    <div class="btn-container" v-if="!isDesktop">
      <button
        @click="changeCard(current)"
        v-for="(controll, current) in depoimentos"
        class="controller"
        :class="active == current ? 'active' : ''"
      ></button>
    </div>
  </div>
</div>
</template>
<script>
  export default {
    data() {
      return {
        active: 0,
        isDesktop: false,
        size: 0,
        depoimentos: [
          {
            id: 0,
            image: "carlos-eduardo",
            cliente: "Carlos Eduardo Amaral",
            cargo: "CEO da Amaral Mídia",
            descricao: `A mpays foi a plataforma onde eu tive a maior 
            taxa de aprovação de crédito do mercado.`,
          },
          {
            id: 1,
            image: "renato-laureano",
            cliente: "Renato Laureano",
            cargo: "Fundador da Anellimn Store",
            descricao: `O principal diferencial é a taxa de cartão recusado 
            ser muito baixa, aumentando nossa taxa de conversão e o faturamento.”`,
          },
          {
            id: 2,
            image: "armando-girao",
            cliente: "Armando Girão",
            cargo: "Fundador da Orion E-commerce",
            descricao: `Depois de muito pesquisar, decidi migrar para a mpays e 
            já nas primeiras semanas nossa taxa de conversão subiu para 94%.`,
          },
        ],
      };
    },
    methods: {
      changeCard(key) {
        this.active = key;
      },
      updateSize() {
        this.size = window.innerWidth;
      },
    },
    watch: {
      size() {
        this.isDesktop = this.size > 768 ? true : false;
      },
    },
    mounted() {
      window.addEventListener("DOMContentLoaded", this.updateSize);
      window.addEventListener("resize", this.updateSize);
    },
    beforeDestroy() {
      window.removeEventListener("DOMContentLoaded", this.updateSize);
      window.addEventListener("resize", this.updateSize);
    },
  };
</script>
<style scoped>
  @import url("https://fonts.googleapis.com/css2?family=Mulish&display=swap");

  #depoimentos {
    padding: 100px 0 100px 0;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  h2 {
    margin-bottom: 15px;
  }

  .card-depoimento {
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    color: #333;
  }

  .subtitle {
    margin-bottom: 40px;
  }
  .card-image {
    width: 200px;
    height: 200px;
    border-radius: 50%;
    background: rgb(29, 0, 0);
  }

  .card-image img {
    width: 100%;
  }

  .quote-icon {
    margin-block: 46px 30px;
  }

  .card-depoimento p {
    width: 256px;
    font-family: "Mulish", sans-serif;
  }

  .card-depoimento p,
  .card-depoimento h5 {
    font-size: 14px;
    font-weight: 400;
  }
  .card-depoimento h4 {
    font-size: 18px;
    margin-block: 16px 5px;
    font-weight: 500;
  }
  .btn-container {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-top: 60px;
  }
  .controller {
    background: var(--gray);
    width: 12px;
    height: 12px;
    border-radius: 50%;
    margin-right: 15px;
  }
  .active {
    background: var(--emphasis);
    width: 16px;
    height: 16px;
  }

  @media screen and (min-width: 768px) {
    .card-row {
      display: flex;
    }
    .card-depoimento{
      margin-right: 30px;
    }
  }
</style>
