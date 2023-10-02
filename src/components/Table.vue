<template>
  <div id="table-container">
    <h2>Tabela de Valores</h2>
    <p class="subtitle">Tabela para volume de vendas até R$ 100.0000,00</p>
    <div class="table">
      <div class="card">
        <div class="card-header">Débito</div>
        <div v-for="(item, index) in debito" :key="index">
          <div class="card-flags">
            {{ item.flag }}
          </div>
          <div class="card-options">
            <div class="option" v-for="(option, opt) in item.option" :key="opt">
              {{ opt == 0 ? "Padrão" : "Caixa Rápido" }} :
              {{ option !== "-" ? option : "-" }}
            </div>
          </div>
        </div>
      </div>

      <div class="card">
        <div class="card-header">Tarifas de antecipação</div>
        <div v-for="(item, index) in antecipacao" :key="index">
          <div class="card-flags">
            {{ item.flag }}
          </div>
          <div class="card-options">
            <div class="option" v-for="(option, opt) in item.option" :key="opt">
              {{ opt == 0 ? "Padrão" : "Caixa Rápido" }} :
              {{ option !== "-" ? option : "-" }}
            </div>
          </div>
        </div>
        <span style="background: var(--green-tea); display: block">
          *Por parcela</span
        >
      </div>

      <div class="card">
        <div class="card-header">Prazo de antecipação</div>
        <div v-for="(item, index) in prazo" :key="index">
          <div class="card-flags">
            {{ item.flag }}
          </div>
          <div class="card-options">
            <div class="option" v-for="(option, opt) in item.option" :key="opt">
              {{ opt == 0 ? "Padrão" : "Caixa Rápido" }} :
              {{ option !== "-" ? option : "-" }}
            </div>
          </div>
        </div>
      </div>
      <div class="card">
        <div class="card-header">Demais tarifas</div>
        <div v-for="(item, index) in demaisTarifas" :key="index">
          <div class="card-flags">
            {{ item.flag }}
          </div>
          <div class="card-options">
            <div
              class="option tarifas"
              v-for="(option, opt) in item.option"
              :key="opt"
            >
              {{ option }}
            </div>
          </div>
        </div>
      </div>
      <div class="caption">
        <p>Dados referentes a dezembro de 2022.</p>
        <p>Válidos até janeiro de 2023.</p>
      </div>
    </div>
  </div>
</template>
<script>
  export default {
    data() {
      return {
        debito: [
          {
            flag: "Visa  |  Mastercard  |  Diners Club Intl.",
            option: ["3%", "2%"],
          },
          {
            flag: "ELO",
            option: ["3%", "2%"],
          },
          {
            flag: "AMERICAN EXPRESS",
            option: ["3%", "2%"],
          },
          {
            flag: "HIPERCARD",
            option: ["3%", "2%"],
          },
        ],
        antecipacao: [
          {
            flag: "Taxa de antecipação - crédito à vista",
            option: ["3%", "2%"],
          },
          {
            flag: "Taxa de antecipação - crédito a prazo*",
            option: ["3%", "2%"],
          },
        ],
        prazo: [
          {
            flag: "Crédito à vista",
            option: ["10 dias", "2 dias"],
          },
          {
            flag: "Parcelado",
            option: ["30 dias", "3 dias"],
          },
        ],
        demaisTarifas: [
          {
            flag: "Boleto por compensação",
            option: ["3,49"],
          },
          {
            flag: "PIX",
            option: ["1,19%"],
          },
          {
            flag: "Taxa por transação",
            option: ["R$ 0,90"],
          },
          {
            flag: "Saque",
            option: ["R$ 3,00"],
          },
        ],
      };
    },
  };
</script>
<style scoped>
  #table-container {
    display: flex;
    flex-direction: column;
    position: absolute;
    left: 0;
    width: 100%;
    background: var(--green-tea);
    padding-top: 50px;
    padding-bottom: 500px;
    padding-inline: 30px;
  }
  .table {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  h2 {
    font-size: 28px;
    text-align: center;
  }

  .subtitle {
    margin-block: 7px 13px;
  }

  .card {
    border-radius: 5px !important;
    background: #fff;
    width: clamp(300px, 75%, 700px);
    margin-bottom: 36px;
  }

  .card-flags,
  .card-header,
  .card-options,
  .option {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 36px;
  }
  .card-header {
    height: 36px;
  }

  .card-flags {
    background: #9a9fa7;
    padding: 5px 31px;
  }

  .card-flags,
  .card-options {
    color: #fff;
  }
  .card-options {
    width: 100%;
    display: flex;
  }

  .card-options .option {
    width: 50%;
    background: var(--emphasis);
  }
  .card-options .option:last-child {
    background: var(--sky);
  }

  .card-options .tarifas,
  .card-options .tarifas:last-child {
    width: 100%;
    background: var(--emphasis);
  }
  @media screen and (min-width: 768px) {
.subtitle{
  text-align: center;
}
  }
</style>
