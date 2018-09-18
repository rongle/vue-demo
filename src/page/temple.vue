<template>
  <div class="main">
    <div class="login">
      <el-form ref="form" :rules="rules" :model="user">
        <el-header>欢迎登录</el-header>
        <el-form-item prop="name">
          <el-input v-model="user.name" placeholder="请输入用户名"></el-input>
        </el-form-item>
        <el-form-item prop="password" style="margin-bottom: 10px">
          <el-input type="password" v-model="user.password" placeholder="请输入密码"></el-input>
        </el-form-item>
        <el-form-item style="text-align: left; margin-bottom: 10px">
          <el-checkbox label="记住密码" style=""></el-checkbox>
        </el-form-item>
        <el-form-item style="margin-bottom: 0px">
          <el-button type="primary" style="width: 100%; margin-bottom: 0px" @click="submitForm('form')">登录</el-button>
        </el-form-item>
      </el-form>
    </div>
  </div>
</template>
<script>

export default {
  data () {
    return {
      user: {
        name: 'admin',
        password: '123456'
      },
      rules: {
        name: { required: true, message: '请输入活动名称', trigger: 'blur' },
        password: {required: true, message: '请输入密码', trigger: 'blur'}
      }
    }
  },

  methods: {
    submitForm (formName) {
      this.$refs[formName].validate((valid) => {
        if (valid) {
          this.$router.push('/')
        } else {
          console.log('error submit!!')
          return false
        }
      })
    }
  }
}
</script>
<style>
.login {
  background-color: #fff;
  width: 250px;
  margin: auto;
  padding: 30px 48px 30px 48px;
  position: absolute;
  top: 25%;
  left: 37.5%;
  border-radius:5px;
}
.main {
  height: 964px;
  background-color: rgba(0,0,0,.08);
}
</style>
