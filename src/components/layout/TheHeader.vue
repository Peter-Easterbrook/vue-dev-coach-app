<template>
  <header>
    <nav>
      <h1><routerLink to="/">Find a Coach</routerLink></h1>
      <ul>
        <li><routerLink to="/coaches">All Coaches</routerLink></li>
        <li v-if="isLoggedIn">
          <routerLink to="/requests">Requests</routerLink>
        </li>
        <li v-else><routerLink to="/auth">Login</routerLink></li>
        <li v-if="isLoggedIn">
          <base-button @click="logout">Logout</base-button>
        </li>
      </ul>
    </nav>
  </header>
  <h2></h2>
</template>

<script>
export default {
  computed: {
    isLoggedIn() {
      return this.$store.getters.isAuthenticated;
    }
  },
  methods: {
    logout() {
      this.$store.dispatch('logout');
      this.$router.replace('/coaches');
    }
  }
};
</script>

<style scoped>
header {
  position: sticky;
  top: 0;
  margin: 0;
  min-width: 100%;
  height: 5rem;
  background-color: #000913;
  display: flex;
  justify-content: center;
  align-items: center;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
}

header a {
  text-decoration: none;
  color: #a2cff4;
  display: inline-block;
  padding: 0.75rem 1.5rem;
  border: 1px solid transparent;
  border-radius: 0.3rem;
}

a:active,
a:hover,
a.router-link-active {
  border: 1px solid #a2cff4;
}

h1 {
  margin: 0;
  font-weight: 200;
}

h1 a {
  color: #f7f7f7;
  margin: 0;
}

h1 a:hover,
h1 a:active,
h1 a.router-link-active {
  border-color: transparent;
}

header nav {
  width: 90%;
  margin: auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

header ul {
  list-style: none;
  margin: 0;
  padding: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 0.3rem;
}

li {
  margin: 0 0.5rem;
  /* box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26); */
}
</style>
