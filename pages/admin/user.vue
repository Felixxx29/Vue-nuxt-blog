<template>
  <div>
    <el-form
      @submit.native.prevent="onSubmit"
      :model="controls"
      :rules="rules"
      ref="form">
      <h2>
        Войти в панель администратора
      </h2>
      <el-form-item label="Логин" prop="login">
        <el-input v-model.trim="controls.login"/>
      </el-form-item>
      <div class="mb2">
        <el-form-item label="Пароль" prop="password">
          <el-input v-model.trim="controls.password" type="password"/>
        </el-form-item>
      </div>

      <el-form-item>
        <el-button
          type="primary"
          native-type="submit"
          round
          :loading="loading"
        >
          Войти
        </el-button>
      </el-form-item>
    </el-form>
  </div>
</template>

<script>
  export default {
    name: "user",
    layout: "admin",
    middleware: ['admin-auth'],
    data() {
      return {
        loading: false,
        controls: {
          login: '',
          password: '',
        },
        rules: {
          login: [
            {required: true, message: 'Введите логин', trigger: 'blur'},
          ],
          password: [
            {required: true, message: 'Введите пароль', trigger: 'blur'},
            {min: 6, massage: 'Пароль должен бытть не менее 6 символов', trigger: 'blur'}
          ],
        }
      }
    },
  }
</script>

<style scoped>

</style>
