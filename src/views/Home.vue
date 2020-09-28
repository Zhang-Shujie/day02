<template>
  <div>
    <van-nav-bar title="我的" left-arrow  />

    <van-cell-group >
  <van-cell @click="onClickLeft">
    <template #icon>
     
     <van-image
  round
  width="60px"
  height="60px"
  src="https://img.yzcdn.cn/vant/cat.jpeg"
/>
    </template>

<template #title>
  <div style="font-size:18px;margin:5px 10px;" v-if="username==''">
    登录/注册
  </div>
  <div>
    {{username}}
  </div>
</template>

<template #label>
<div style="font-size:18px;margin:10px 10px;">
  绑定手机号
</div>
</template>
<template #right-icon>
                    <div class="login-right-icon">
                        <van-icon name="arrow" />
                    </div>
                </template>
  </van-cell>
</van-cell-group>
  </div>
</template>

<script>
export default {
  data() {
    return {
       username: ''
    };
  },
  methods: {
    onClickLeft() {
      if(this.username ==''){
        this.$router.push({
        path: "/user"
      });
      }else{
        this.$router.push({
          path:'/about'
        })
      }
      
    },
   
  },
   created(){
      let username = localStorage.username
      if(username){
        this.username = username
      }
    }
};
</script>

<style>
.login-right-icon{
      display: flex;
      align-items: center;
  }
</style>