<script setup lang="ts">
import { reactive, ref } from 'vue'
import type { FormInstance, FormRules } from 'element-plus'
import DefaultButton from '../DefaultButton.vue'

interface RuleForm {
  email: string
  password: string
}

const ruleFormRef = ref<FormInstance>()
const ruleForm = reactive<RuleForm>({
  email: '',
  password: ''
})
const rules = reactive<FormRules<RuleForm>>({
  email: [{ required: true, message: 'Por favor, insira um e-mail válido.', trigger: 'blur' }],
  password: [{ required: true, message: 'Por favor, insira uma senha válida.', trigger: 'blur' }]
})
</script>

<template>
  <div class="login-forms">
    <div class="titles">
      <h1>Seja bem vindo(a)!</h1>
      <h3>Insira seus dados para fazer o login.</h3>
    </div>
    <div class="forms-content">
      <el-form
        ref="ruleFormRef"
        :model="ruleForm"
        :rules="rules"
        label-width="auto"
        class="demo-ruleForm"
        size="default"
        status-icon
        label-position="top"
      >
        <el-form-item label="E-mail" prop="email">
          <el-input v-model="ruleForm.email" />
        </el-form-item>
        <el-form-item label="Senha" prop="password">
          <el-input v-model="ruleForm.password" show-password />
        </el-form-item>
        <el-form-item>
          <default-button :label="'Entrar'" :variant="'blue'" />
        </el-form-item>
      </el-form>
    </div>
  </div>
</template>

<style scoped lang="less">
.login-forms {
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;

  .titles {
    display: flex;
    flex-direction: column;
    justify-content: center;
    gap: 4px;
    margin-bottom: 32px;
  }
}
</style>
