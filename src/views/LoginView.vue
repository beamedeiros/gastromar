<script setup lang="ts">
import LoginForm from '@/components/login/LoginForm.vue'
</script>

<template>
  <div class="login-page">
    <div class="img-content">
      <img src="../assets/login/login.jpg" alt="comida" />
      <div class="centered">
        <img src="../assets/logosimples.png" alt="logo gastromar" />
      </div>
      <div class="bottom">
        <img src="../assets/marefica.png" alt="se a maré te trouxe, fica" />
      </div>
    </div>
    <div class="login-form">
      <login-form />
      <div class="register-option">
        <h5>ou</h5>
        <h4>Não tem uma conta? <span>Cadastre-se</span></h4>
      </div>
    </div>
  </div>
</template>

<style scoped lang="less">
.login-page {
  display: grid;
  grid-template-columns: 1fr 1fr;
  padding: 8px;

  .img-content {
    position: relative;
    border-radius: 8px 8px 8px 8px;
    width: 50vw;
    height: calc(100vh - 16px);
    background-color: black;
    z-index: 5;
    color: white;

    img {
      border-radius: 8px 8px 8px 8px;
      width: 50vw;
      height: calc(100vh - 16px);
      opacity: 0.65;
    }

    .centered {
      position: absolute;
      top: 50%;
      left: 45%;
      transform: translate(-50%, -50%);

      img {
        width: 120%;
        height: 120%;
        opacity: 10;
      }
    }

    .bottom {
      position: absolute;
      top: 90%;
      left: 50%;
      transform: translate(-50%, -50%);

      img {
        width: 100%;
        height: 100%;
        opacity: 10;
      }
    }
  }

  .login-form {
    display: flex;
    justify-content: center;
    padding: 170px;
    flex-direction: column;
    align-items: center;

    .register-option {
      display: flex;
      gap: 16px;
      flex-direction: column;
      align-items: center;
      margin-top: 8px;

      span {
        text-decoration: underline;
        font-weight: 700;
        color: #1a4170;
      }
    }
  }
}
</style>
