<template>
    <el-row id="welcome">
      <el-col :xs="24" :sm="12" :md="11" :lg="11" :xl="14" class="contentLeft">
        <iframe :src="catUrl" frameborder="0"   scrolling="no" width="100%;" height="580px;"></iframe>  
      </el-col>
      <el-col :xs="0" :sm="12" :md="13" :lg="13" :xl="10" class="contentRight">
        <div class="animated slideInDown" :class="{'shake':isShake}">
          <img :src="myLogo" alt="" class="logo" @click="rotate">
        </div>
      </el-col>
    </el-row>
</template>

<script>
export default {
  name: 'welcome',
  data() {
    return {
      catUrl: '',
      myLogo: '',
      isShake: false
    }
  },
  created() {
    this.catUrl = '../../../../static/cat/index2.html'
    this.myLogo = '../static/images/myLogo.jpg'
  },
  mounted() {},
  methods: {
    rotate() {
      this.isShake = !this.isShake
      console.log(1)
    }
  }
}
</script>

<style lang="scss" scoped>
#welcome {
  .contentRight {
    .logo {
      width: 6rem;
      height: 6rem;
      border: 3px solid rgba($color: #db351d, $alpha: 0.8);
      border-radius: 50%;
      margin: 10% 0 0 5%;
      transition: all 1s;
      &:hover {
        transform: rotate(360deg);
      }
    }
  }
}
</style>

