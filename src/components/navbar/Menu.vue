<template>
  <header>
    <button @click="openMenu" class="btn-hamburger"><img src="./assets/hamburger.svg" /></button>
    <a href="/"><img src="./assets/logo.svg" /></a>
    <button class="login"><img src="./assets/profile.svg" /></button>
<nav>
    <ul :class="isOpen ? 'menuClose': 'menuOpen'">
        <button @click="openMenu" class="btn-close"><img src="./assets/close.svg" /></button>
      <li v-for="(link, n) in menu" :key="n">
        <a  @click="openMenu" :href="link.to">{{link.label}}</a>
    </li>
    <button class="btn-login">Entrar</button>
</ul>
</nav>
    
  </header>
</template>
<script>
export default{
    data(){
        return{
            isOpen: false,
            menu:[
                {label: 'Soluções',
                to: '#solucoes'},
                {label: 'Tarifas',
                to: '#simulation'},
                {label: 'Depoimentos',
                to: '#depoimentos'},
                {label: 'Cadastro',
                to: '#cadastro'},
                {label: 'Contato',
                to: ''},
            ]
        }
    },
    methods:{
        openMenu(){
            this.isOpen = !this.isOpen
        }
    }
}
</script>
<style scoped>
  header {
    display: flex;
    justify-content: space-around;
    align-items: center;
    color: white ;
    height: 90px;
  }
  .btn-hamburger {
    width: 25px;
    height: 25px;
  }

  .btn-close{
    position: absolute;
    right: 20px;
    top: 20px;
  }

  .menuClose{
        position: absolute;
        z-index: 10;
        top: 0;
        left: 0;
        height: 100vh;
        width: 100vw;
        background: white;
        padding:55px 45px;
    }

    .menuOpen{
        display: none;
    }

    nav > ul > li > a{
        display: inline-block;
        height: 40px;
        width: 100%;
    }


  @media screen and (min-width: 768px) {
    .btn-hamburger, .login {
      display: none;
    }
    nav > ul{
        /* border: 1px solid goldenrod; */
        display: flex;
        align-items: center;
    }
    nav > ul > li > a{
        margin-right: 30px;
        color: white !important;
        
    }
    .btn-login{
        padding: 6px 29px;
        border: 1px solid white;
        border-radius: 5px;

    }

    .menuOpen{
        display: flex;
        align-items: center;
    }
    nav > ul > li > a{
        display: inline;
    }

    .btn-close{
        display: none;
    }
  }
</style>
