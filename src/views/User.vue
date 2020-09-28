<template>
  <div>
      <van-nav-bar
  title="登录"
  left-arrow
  @click-left="onClickLeft"
 
/>


<van-form >
  <van-field
    v-model="username"
   
    label="用户名"
    placeholder="用户名"
    :rules="[{ required: true, message: '请填写用户名' },{pattern:/^[1][3,5,6,7,8,9,][0-9]{9}$/,message:'请输入正确的11位手机号'}]"
  />
  <van-field
    v-model="password"
    type="password"
    label="密码"
    placeholder="密码"
    :rules="[{ required: true, message: '请填写密码' },{pattern:/^\w{6,}$/,message:'密码不正确'}]"
  />
  <div style="margin: 16px;">
    <van-button round block type="info" @click="onSubmit">
      登录
    </van-button>
  </div>
</van-form>


  </div>
</template>

<script>
export default {
data(){
    return{
        username:'',
        password:''
    }
},
methods:{
    onClickLeft(){
        this.$router.push({
            path:'/'
        })
    },
    onSubmit(){
        if(!this.username.match(/^[1][3,5,6,7,8,9,][0-9]{9}$/)){
            return
        }
        if(!this.password.match(/^\w{6,}$/)){
            return
        }
        localStorage.username =this.username
        this.$router.push({
            path:'/'
        })
    }
}
}
</script>

<style>

</style>