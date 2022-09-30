<template>
  <a class="user-profile-link">
    <img class="user-img" :src="userImg" alt="user img">
  </a>
</template>

<script>
export default {
  name: "HeaderUserProfile",
  data(){
    return{
      userImg:'https://i.pinimg.com/736x/10/ea/3b/10ea3b0bf865aff1573039c8fe9e4447.jpg'
    }
  }
}
</script>

<style scoped lang="scss">
.user-profile-link,.user-img {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  .user-img{

  }
}
</style>