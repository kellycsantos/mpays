<template>
  <div id="modal-cookie" v-if="cookie">
    <p>
      Ao usar o mpays, você concorda com nossa <span>Política de Cookies</span>.
    </p>
    <button @click="okCookie">OK</button>
  </div>
</template>
<script>
  export default {
    data(){
        return{
            cookie: true
        }
    },
    methods: {
      okCookie(){
        this.cookie = false
      },
    },
    mounted(){
        this.cookie = true
    }
  };
</script>
<style scoped>
  #modal-cookie {
    display: flex;
    justify-items: center;
    align-items: center;
    position: relative;
    top: -25vh;
    margin: auto;
    background: #fff;
    padding: 33px 43px;
    border-radius: 16px;
    box-shadow: -5px 5px 10px rgba(52, 53, 54, 0.6);
    width: clamp(200px, 70%, 766px);
  }

  #modal-cookie p {
    font-size: 18px;
  }
  #modal-cookie span {
    color: var(--emphasis);
    font-weight: 500;
  }

  #modal-cookie button {
    background: var(--emphasis);
    min-width: 70px;
    height: 38px;
    text-align: center;
    color: #fff;
    font-weight: 500;
    border-radius: 5px;
    margin-left: 40px;
  }
</style>
