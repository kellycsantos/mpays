<template>
  <div id="simulation">
    <TableValores v-if="showTable" />
    <button v-if="showTable" @click="taxas" class="btn-close">
      <img src="../assets/close.svg" />
    </button>
    <div>
      <h2>Simulador de vendas mpays</h2>
      <p class="subtitle">
        Veja quanto você recebe nas vendas no crédito, débito e parcelado.
      </p>
    </div>

    <div class="form-container">
      <div class="input-container">
        <label>Valor</label>
        <input type="text" placeholder="R$ 1.000,00" />
        <label>Forma de pagamento</label>
        <div class="select-container">
          <select>
            <option value="">Crédito à vista</option>
          </select>
        </div>
      </div>

      <div>
        <h3>VOCÊ RECEBE:</h3>
        <table>
          <tr>
            <td>NA HORA</td>
            <td>Não disponível</td>
          </tr>
          <tr>
            <td>EM 10 DIAS</td>
            <td>R$ 949, 70</td>
          </tr>
          <tr>
            <td>EM 30 DIAS</td>
            <td>R$ 959, 70</td>
          </tr>
          <caption align="bottom">
            Todas as simulações usam as taxas iniciais informadas no site.
            <button @click="taxas">
              <img class="help-icon" src="../assets/help-icon.svg" />
            </button>
          </caption>
        </table>
      </div>
    </div>
  </div>
</template>
<script>
  import TableValores from "../components/Table.vue";
  export default {
    data() {
      return {
        showTable: false,
      };
    },
    components: {
      TableValores,
    },
    methods: {
      taxas() {
        this.showTable = !this.showTable;
      },
    },
  };
</script>
<style scoped>
  #simulation {
    background: var(--green-tea);
    padding: 45px 30px;
    color: var(--secondary);
    
  }

  .subtitle {
    margin-block: 14px 40px;
  }

  h2 {
    width: 220px;
    font-size: 28px;
  }

  .form-container {
    display: flex;
    flex-direction: column;
    background: #fff;
    border-radius: 16px;
    padding: 42px 28px 51px;
  }

  table {
    margin-top: 24px;
  }

  td {
    display: inline-flex;
    margin-bottom: 24px;
    width: 50%;
  }

  caption {
    text-align: left;
    font-size: 12px;
  }

  .btn-close {
    position: absolute;
    right: 25px;
    z-index: 20;
  }

  @media screen and (min-width: 768px) {
    #simulation {
      display: flex;
      align-items: center;
      justify-content: space-around;
      position: relative;
    }

    h2 {
      font-size: 49px;
      width: 380px;

    }
    .subtitle {
      font-size: 18px;
      width: 350px;
    }
    .form-container {
      display: flex;
      flex-direction: row;
    }

    .input-container {
      margin-right: 40px;
    }

    .btn-close {
      position: absolute;
      left: 95vw;
      top: -650px;
      z-index: 30;
    }
  }
</style>
