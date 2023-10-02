<template>
  <div id="termo-uso" v-if="isOpen">
    <button @click="closeTermo(isOpen)" class="btn-close"><img src="../assets/close.svg"></button>
    <h2>COMO FUNCIONA A PLATAFORMA MPAYS</h2>
    <p>
      Fizemos o máximo para reduzir e simplificar as regras do nosso Site e
      SaaS. Por isso, separamos abaixo os pontos mais importantes para você, que
      também podem ser lidos de forma bem completa e detalhada nos nossos Termos
      de Uso.
    </p>
    <p>
      Além disso, estamos sempre disponíveis para tirar qualquer dúvida que você
      tenha na plataforma MPays através do e-mail: financeiro@multti.com ou pelo
      telefone (51) 99980-0020.
    </p>
    <h3>1) O que fazemos?</h3>
    <p>
      Somos uma empresa de tecnologia que desenvolve soluções inteligentes para
      transações de pagamento realizados no e-commerce com cartão de crédito,
      débito, boleto e PIX.
    </p>

    <p>
      O foco principal da empresa é o desenvolvimento de Sistemas Gerenciais de
      Negócios com um olhar voltado para modelos de negócio tipo SaaS e que
      possuam intermediação de pagamentos.
    </p>
    <p>
      Atualmente nossos serviços estão disponíveis em dois planos de
      contratação, o plano: (i) padrão e o (ii) caixa rápido. Além disso,
      oferecemos serviços para solicitação de saque dos valores disponíveis,
      antecipação de recebível de crédito à vista, com prazo de até 2 (dois)
      dias úteis (disponível no plano Caixa Rápido) e em até 10 (dez) dias úteis
      no plano Padrão. Para a antecipação de recebíveis de crédito parcelado o
      prazo é de 3 (três) dias úteis para o plano de Caixa Rápido e 30 (trinta)
      dias úteis para o plano Padrão.
    </p>

    <h3>2) Como o nosso SaaS funciona?</h3>
    <p>
      Os usuários terão que criar uma conta de acesso (login e senha) para
      acessar a plataforma e os serviços. Atualmente há três tipos de usuários:
    </p>
    <ul>
      <li>
        Administrador Mpays: Usuário master, onde terá acesso aos dados de todas
        as lojas, extratos das transações, extratos das contas, solicitações de
        saque, usuários cadastrados pelas lojas e configuração das taxas dos
        planos.
      </li>
      <li>
        Administrador loja: Usuário que terá acesso aos dados da de sua empresa,
        extrato das transações, extrato da sua conta, solicitações de saque e
        cadastro de usuários que poderão acessar as informações da loja.
      </li>
      <li>
        Usuário da loja: Usuário que o administrador cadastrar. Ele poderá ser
        limitado a visualização dos menus da plataforma. Você poderá consultar o
        extrato da conta onde é apresentada todas as movimentações da conta de
        sua empresa e a possibilidade de que a empresa cadastre seus
        funcionários para acesso a plataforma de forma personalizada, sendo
        possível bloquear sua visualização a determinadas telas através do
        perfil de acesso do usuário cadastrado pela loja.
      </li>
    </ul>
  </div>
</template>
<script>
export default{
    props:{
        isOpen: {
            type: Boolean,
            default: false
        }
    },
    data(){
        return{
            showTermo: true
        }
    },
    methods:{
        closeTermo(val){
            this.showTermo = val
        }
    }
}
</script>
<style scoped>
  #termo-uso {
    display: flex;
    flex-direction: column;
    color: #000 !important;
    padding: 0 20px;
  }

  button {
    align-self: flex-end;
  
  }

  h2 {
    font-size: 18px;
    width: 80%;
    color: #000 !important;
  }

  h3 {
    font-size: 15px;
  }

  p {
    font-size: 14px;
    margin-block: 14px;
    line-height: 21px;
  }

  li {
    font-size: 14px;
    list-style-type: disc;
    margin-block: 14px;
    padding-left: 10px;
    list-style-position: inside;
  }
</style>
