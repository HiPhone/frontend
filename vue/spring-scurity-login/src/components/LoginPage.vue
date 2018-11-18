<template>
  <div>
    <Row type="flex" justify="center">
    <Card class="card-style">
      <p slot="title" >登录</p>
      <Form ref="loginForm" :model="loginModel" :rules="loginRules">
        <FormItem prop="username">
          <Input type="text" v-model="loginModel.username" placeholder="请输入用户名">
            <Icon type="ios-person" slot="prepend"></Icon>
          </Input>
        </FormItem>
        <FormItem prop="password">
          <Input type="password" v-model="loginModel.password" placeholder="请输入密码">
            <Icon type="ios-lock" slot="prepend"></Icon>
          </Input>
        </FormItem>
      </Form>
      <Button type="primary" long @click="login">登录</Button>
    </Card>
    </Row>
  </div>
</template>

<script>
import api from './utils/api.js'
import qs from 'qs'
export default {
  data() {
    return {
      loginModel: {
        username: '',
        password: ''
      },
      loginRules: {
        username: [
          {required: true, message: '请输入登录用户名', trigger: 'blur'} 
        ],
        password: [
          {required: true, message: '请输入登录密码', trigger: 'blur'}
        ]
      }
    }
  },
  methods: {
    login: function() {
      this.$refs.loginForm.validate((valid) => {
        if (valid) {
          let data = qs.stringify(this.loginModel);
          axios.post(api.login, data)
            .then(response => {
              
            })
            .catch(error => {

            })
        } else {
          this.$Message.error({
            content: '请填写必要信息!',
            duration: 5
          })
        }
      })
    }
  }
}
</script>

<style>
.card-style {
  width: 400px;
  margin-top: 14%;
}

</style>

