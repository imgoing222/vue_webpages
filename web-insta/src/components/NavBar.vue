<template>
  <div class="nav-bar">
    <b-navbar toggleable="lg" class="navbar d-flex justify-content-between">
      <b-navbar-brand href="#" @click="moveToHome"><img src="@/assets/instagram.png" alt=""></b-navbar-brand>
      <b-form-input size="sm" class="search-input bg-light" placeholder="검색"></b-form-input>
      <div class="nav-bar-items d-flex align-items-center">
        <b-nav-item href="#" @click="moveToHome"><b-icon icon="house-door"></b-icon></b-nav-item>
        <b-nav-item href="#"><b-icon icon="cursor"></b-icon></b-nav-item>
        <b-nav-item href="#"><b-icon icon="plus-square"></b-icon></b-nav-item>
        <b-nav-item href="#"><b-icon icon="compass"></b-icon></b-nav-item>
        <b-nav-item href="#"><b-icon icon="heart"></b-icon></b-nav-item>
        <b-nav-item href="#" @click="moveToProfile"><b-avatar variant="info" :src="user.profile_img_url" size="1.5em"></b-avatar></b-nav-item>
      </div>
    </b-navbar>
  </div>
</template>

<script>
import { mapState } from 'vuex';
export default {
  name: 'NavBar',
  methods: {
    moveToHome: function(){
      this.$router.push({ name: 'Home' })
    },
    moveToProfile: function(){
      this.$router.push({ name: 'Profile' })
    }
  },
  computed: {
    ...mapState(['user'])
  }
}
</script>

<style scoped>

.navbar{
  background-color: #fff;
  border-bottom: 1px solid #dcdcdc;
  padding: 8px 15px;
  width: 100vw;
}

.search-input{
  width: 30vw;
}

li {
  list-style: none;
}

a {
  color: black;
  padding: 12px 12px;
}

</style>