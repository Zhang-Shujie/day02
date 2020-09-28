<template>
  <div>
      <van-nav-bar
  title="个人信息"
  left-arrow
/>

<van-cell-group>
  <van-cell title="头像"  />
  <van-cell title="用户名" :value="username"  />
</van-cell-group>

<van-button block @click="exit" type="danger">退出登录</van-button>

  </div>
</template>

<script>
export default {
data(){
    return{
      username:''
    }
},
created(){
    let username = localStorage.username
    if(username){
      this.username = username
    }
},
methods:{
    exit(){
       this.$dialog.confirm({
         message:'确定要退出吗?'
       }).then(()=>{
         localStorage.removeItem('username')
         this.$router.push({
           path:'/user'
         }).catch(()=>{

         })
       })
     }
  }
}
</script>

<style>

</style>