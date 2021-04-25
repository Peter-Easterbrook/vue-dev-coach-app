<template>
  <li>
    <div>
      <a :href="emailLink"> {{ email }} </a>
    </div>
    <p>{{ message }}</p>
  </li>
</template>

<script>
export default {
  props: ['email', 'message'],
  computed: {
    emailLink() {
      return 'mailto' + this.email;
    }
  }
};
</script>
<style scoped>
li {
  margin: 1rem 0;
  border: 1px solid #ccc;
  padding: 1rem;
}

a {
  color: #0d3f63;
  text-decoration: none;
  font-weight: 300;
}

a:hover,
a:active {
  color: #1d8cdc;
}

p {
  margin: 0.5rem 0 0 0;
  font-weight: 200;
}
</style>
