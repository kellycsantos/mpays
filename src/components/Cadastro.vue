<template>
  <div id="cadastro">
    <h2>Crie sua conta</h2>
    <p class="subtitle">
      Preencha o formulário ao lado para cadastrar-se no mpays.
    </p>

    <ModalCadastro v-if="cadastroCompleto" />

    <div class="form">
      <label>Nome e sobrenome *</label>
      <input type="text" placeholder="Nome" />
      <label>E-mail *</label>
      <input type="text" placeholder="E-mail" />
      <label>Telefone *</label>
      <input type="text" placeholder="Telefone" />
      <label>Senha *</label>
      <input type="password" :class="isNull ? 'null' : ''" v-model="password" />
      <button class="btn-cadastrar" @click="cadastrar">Cadastrar</button>
    </div>
  </div>
</template>
<script>
  import ModalCadastro from "./ModalCadastro.vue";
  export default {
    components: {
      ModalCadastro,
    },
    data() {
      return {
        cadastroCompleto: false,
        isNull: true,
        password: "",
      };
    },
    methods: {
      cadastrar() {
        this.cadastroCompleto = true;
      },
    },
    watch: {
      password(val) {
        this.isNull = val.length == 0 ? true : false;
      },
    },
  };
</script>
<style scoped>
  #cadastro {
    padding: 0 30px;
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .subtitle {
    padding-block: 15px 40px;
  }

  .form {
    display: flex;
    flex-direction: column;
    align-items: center;
    max-width: 700px;
  }

  label {
    align-self: start;
  }
  .null {
    background: url("../assets/password-bg.svg") no-repeat left 20px center;
  }
  .btn-cadastrar {
    background: var(--primary);
    width: 350px;
    color: #fff;
    padding-block: 8px;
    text-align: center;
    font-size: 14px;
    border-radius: 5px;
    font-weight: 500;
  }
</style>
