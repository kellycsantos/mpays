<template>
  <div id="cadastro-modal" v-if="showModal">
    <button @click="closeModal"><img src="../assets/close.svg" /></button>
    <img src="../assets/check.svg" />
    <h3>
      Finalize seu cadastro na plataforma e acesse seu e-mail para validação.
    </h3>
    <button class="login">Acessar plataforma</button>
  </div>
</template>
<script>
export default{
    data(){
        return{
            showModal: true,
        }
    },
    methods:{
        closeModal(){
            this.showModal = false
        }
    }
}
</script>
<style scoped>
  #cadastro-modal {
    border-radius: 24px;
    background: white url("../assets/background-modal-mobile.svg") bottom
      no-repeat;
    position: absolute;
    left: 50%;
    transform: translate(-50%, -20%);
    margin: auto;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 20px 10px 68px;
    box-shadow: 5px 5px 10px rgba(52, 53, 54, 0.6);
  }

  #cadastro-modal h3 {
    line-height: 32px;
    font-size: 18px;
    width: 292px;
    text-align: center;
  }

  #cadastro-modal img {
    margin-bottom: 50px;
  }

  button {
    align-self: flex-end;
  }

  #cadastro-modal .login {
    background: var(--primary);
    color: #fff;
    width: 270px;
    align-self: center;
    text-align: center;
    padding-block: 10px;
    border-radius: 5px;
  }
</style>
