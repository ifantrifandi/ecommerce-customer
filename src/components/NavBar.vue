<template>
<div>
  <!-- Will edited into history, cart and logout -->
  <b-navbar type="dark" variant="custom">
    <b-navbar-brand href="#" v-on:click.prevent="home">Home</b-navbar-brand>

    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <!-- Right aligned nav items -->
      <b-navbar-nav class="ml-auto">
          <button class="box-icon" v-on:click.prevent="cart">
            <img src="../assets/cart.png" alt="cart" class="icon-nav">
          </button>
        <b-navbar-nav>
          <b-nav-item href="#" v-on:click.prevent="logout">Logout</b-nav-item>
        </b-navbar-nav>
      </b-navbar-nav>

  </b-navbar>
</div>
</template>

<script>
export default {
  name: 'NavBar',
  methods: {
    logout () {
      localStorage.clear()
      this.$store.commit('SET_STATUS_LOGIN', false)
      this.$router.push({ name: 'Login' })
    },
    cart () {
      this.$router.push({ name: 'Cart' })
    },
    home () {
      this.$router.push({ name: 'Home' })
    }
  }
}
</script>

<style>

</style>
