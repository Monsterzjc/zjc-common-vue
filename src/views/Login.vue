<template>
  <div class="box">
    <div class="login">
      <el-form
        :model="loginForm"
        status-icon
        :rules="loginRules"
        ref="loginForm"
      >
        <el-form-item prop="username">
          <el-input
            v-model="loginForm.username"
            placeholder="请输入用户名"
            prefix-icon="el-icon-user"
            autocomplete="off"
          ></el-input>
        </el-form-item>
        <el-form-item prop="password">
          <el-input
            type="password"
            v-model="loginForm.password"
            placeholder="请输入密码"
            prefix-icon="el-icon-lock"
            autocomplete="off"
          ></el-input>
        </el-form-item>
        <el-form-item style="height: 30px">
          <div class="register">
            <el-link type="primary" :underline="false">新用户注册</el-link>
            <el-link type="primary" :underline="false">返回主页</el-link>
          </div>
        </el-form-item>
        <el-form-item>
          <el-button
            type="primary"
            @click="submitForm('loginForm')"
            style="width: 100%"
            >登录</el-button
          >
        </el-form-item>
      </el-form>
    </div>
  </div>
</template>

<script>
export default {
  name: "",
  data() {
    return {
      loginForm: {
        username: '',
        password: ''
      },
      loginRules: {
        username: [
          {required: true,message: '请输入用户名',trigger: 'change'}
        ],
        password: [
          {required: true,message: '请输入密码',trigger: 'change'}
        ]
      }
    };
  },
  methods: {
    submitForm(formName) {
        this.$refs[formName].validate((valid) => {
          if (valid) {
            
          } else {
            
            return false;
          }
        });
      },
  }
};
</script>

<style scoped>
.box {
  width: 100%;
  height: 100vh;
  background-image: url("https://gw.alipayobjects.com/zos/rmsportal/FfdJeJRQWjEeGTpqgBKj.png");
  overflow: hidden;
}

.box .login {
  width: 350px;
  height: 500px;
  margin: 150px auto;
}

.box .login .register {
  display: flex;
  justify-content: space-between;
}
</style>
