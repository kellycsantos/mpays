<template>
  <footer>
    <TermoUso  :isOpen="showTermo"/>
    <div class="section01">
      <div class="section-footer">
        <h4>Endereço</h4>
        <p>
          R. dos Andradas, 1234 <br />Centro Histórico Porto Alegre - RS
          <br />90020-008
        </p>
      </div>

      <div class="section-footer">
        <h4>Legal</h4>
        <button @click="mostrar">Termos de uso</button>
        <li>Política de privacidade</li>
      </div>

      <div class="section-footer">
        <h4>Contato</h4>
        <li>contato@mpays.com</li>
        <li>(51) 98314.3325</li>
        <span
          ><img src="../assets/facebook.svg" />
          <img src="../assets/instagram.svg" />
          <img src="../assets/linkedin.svg"
        /></span>
      </div>

      <div class="section-footer">
        <h4>Aceitamos</h4>
        <img src="../assets/bandeiras.svg" />
        <p class="observacao">*Demais cartões sob contratação.</p>
      </div>
      <div class="section-footer">
        <img src="../assets/pci-dss.svg" />
        <img src="../assets/reclame-aqui.svg" />
      </div>
    </div>

    <div class="copyright">
      <p>Copyright @ 2022 mpays</p>
      <img src="../assets/logo.svg" />
    </div>

    <p class="info-text">
      mpays é um produto da Multti Tecnologia e Integrações, empresa brasileira
      registrada no CNPJ nº 33.511.889/0001-20. A atividade de subcredenciamento
      é dispensada de autorização do Banco Central do Brasil, conforme termos da
      Circular nº 3.885/2018. Demais dispositivos aplicáveis, como o disposto
      nas Circulares nº 3.682/2013, 3.886/2018, 3.952/2019 e Resolução nº
      24/2020 são rigorosamente cumpridos.
    </p>
  </footer>
</template>
<script>
import TermoUso from './TermoUso.vue';
export default{
  components:{
    TermoUso
  },
  data(){
    return{
      showTermo: false
    }
  },
  methods:{
    mostrar(){
      this.showTermo = !this.showTermo
    }
  }
}
</script>
<style scoped>
  footer {
    margin-top: 218px;
    color: var(--secondary);
  }
  .section01 {
    display: flex;
    justify-content: space-around;
    flex-wrap: wrap;
  }
  .section-footer {
    width: 136px;
  }

  .section-footer h4 {
    font-size: 18px;
    font-weight: 500;
    margin-block: 50px 23px;
  }
  .section-footer :not(h4) {
    font-size: 12px;
    margin-bottom: 29px;
  }

  .section-footer span {
    display: flex;
    justify-content: space-between;
    width: 60%;
  }

  .observacao {
    font-size: 10px;
  }

  .copyright {
    display: flex;
    justify-content: space-around;
    margin-bottom: 72px;
  }
  .info-text{
   padding: 0 30px 59px;
   text-align: center;
  }
</style>
