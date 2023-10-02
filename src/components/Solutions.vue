<template>
  <div id="solucoes">
    <div
      class="card-container"
      v-for="(solucao, id) in solutions"
      :key="id"
      v-show="solucao.id == active"
    >
    <img :src="`/assets/solucoes/${solucao.image}.svg`" />

      <div class="info-container">
        <h3>{{ solucao.title }}</h3>
        <p>
          {{ solucao.description }}
        </p>

        <a class="subscribe" href="">{{ solucao.labelLink }}</a>
      </div>
    </div>
    <div class="btn-container">
      <button
        @click="changeCard(current)"
        v-for="(controll, current) in solutions"
        class="controller"
        :class="active == current ? 'active' : ''"
      ></button>
    </div>

    <div class="slide">
      <button
        class="controle"
        @click="next()"
        :class="this.active == 0 ? 'hide-controll' : ''"
      >
        <img src="./assets/solutions/arrow-preview.svg" />
      </button>

      <div
        class="card-container-desktop"
        v-for="(solucao, id) in solutions"
        :key="id"
        v-show="solucao.id == active"
      >
        <div class="info-container">
          <h3>{{ solucao.title }}</h3>
          <p>
            {{ solucao.description }}
          </p>

          <a class="subscribe" href="">{{ solucao.labelLink }}</a>
        </div>
        <img :src="`/assets/solucoes/${solucao.image}-desktop.svg`" />
      </div>
      <button
        class="controle"
        @click="next(true)"
        :disabled="this.active == this.solutions.length - 1"
        :class="this.active == this.solutions.length - 1 ? 'hide-controll' : ''"
      >
        <img src="./assets/solutions/arrow-next.svg" />
      </button>
    </div>
  </div>
</template>
<script>
  export default {
    data() {
      return {
        active: 0,

        solutions: [
          {
            id: 0,
            image: "pagamentos",
            title: "Pagamentos com máxima aprovação",
            description: `Venda online com a maior taxa de aprovação possível. 
                    Reduza o número de vendas recusadas, autorize o 
                    maior número de pagamentos, receba e gerencie seu dinheiro de forma flexível.`,
            labelLink: "Cadastre-se",
            link: "/",
          },
          {
            id: 1,
            image: "checkout",
            title: "Checkout de alta conversão",
            description: `Uma solução de checkout com inúmeros recursos para potencializar ainda mais 
                    as suas vendas online. Customize toda a experiência de pagamento, ofereça produtos adicionais,
                     recupere clientes, gere links para que outras pessoas possam promover seus produtos e mais.`,
            labelLink: "Saiba mais",
            link: "/",
          },
          {
            id: 2,
            image: "controle",
            title: "Controle total do seu fluxo financeiro",
            description: `Filtre as informações que você quer ver e acompanhe seu extrato diariamente para 
                    saber quando você vai receber pelas suas vendas. Precisa do dinheiro antes? Antecipe os seus 
                    recebíveis com apenas alguns cliques!`,
            labelLink: "Clique e conheça",
            link: "/",
          },
          {
            id: 3,
            image: "receba",
            title: "Receba as vendas parceladas em até 2 dias úteis",
            description: `Solicite a antecipação de recebíveis online e receba pagamentos com agilidade, 
                    sem burocracia e sem juros abusivos. Vamos ajudar o seu negócio a adquirir capital de giro 
                    recebendo um dinheiro que já é seu!`,
            labelLink: "Aproveite",
            link: "/",
          },
        ],
      };
    },
    methods: {
      changeCard(key) {
        this.active = key;
      },
      next(nextItem) {
        if (nextItem) {
          this.active < this.solutions.length ? this.active++ : "";
        } else {
          this.active == 0 ? "" : --this.active;
        }
      },
    },
  };
</script>
<style scoped>
  #solucoes {
    padding: 100px 30px;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .card-container {
    border-radius: 16px;
    box-shadow: 5px 5px 15px rgba(0, 0, 0, 0.15);
    margin-bottom: 38px;
    max-width: 350px;
  }

  .card-container img {
    width: 100%;
  }

  .info-container {
    padding: 24px 36px;
    color: var(--secondary);
  }

  .info-container p {
    font-size: 14px;
    line-height: 21px;
    margin-block: 26px;
  }

  .info-container .subscribe {
    color: var(--emphasis);
    text-decoration: underline;
  }
  .btn-container {
    display: flex;
    justify-content: center;
    align-items: center;
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

  .slide {
    display: none;
  }

  @media screen and (min-width: 768px) {
    .card-container {
      display: none;
    }
    .slide {
      display: flex;
      align-items: center;
    }

    .controle {
      margin-inline: 78px;
      width: 20px;
    }

    .hide-controll {
      opacity: 0;
    }

    .btn-container {
      display: none;
    }

    .card-container-desktop {
      display: flex;
      flex-direction: row;
      max-width: 916px;
      height: 475px;
      padding: 0 !important;
      box-shadow: 5px 5px 10px rgba(52, 53, 54, 0.247);
      border-radius: 16px;
      border: 1px solid  rgba(52, 53, 54, 0.247);
    }
    .card-container-desktop img {
      height: 519px;
      margin-top: -44px;
    }

    .info-container {
      padding-block: 78px;
    }

    .info-container h3 {
      font-size: 28px;
    }
    .info-container p {
      font-size: clamp(14px,1vw,18px);
      line-height: clamp(18px,1vw,31.9px);
      font-weight: 500;
      width: 140%;
    }
  }
</style>
