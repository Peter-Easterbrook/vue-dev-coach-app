<template>
  <span class="badge" :class="type">
    {{ text }}
  </span>
</template>

<script>
export default {
  props: ['type', 'title'],
  computed: {
    text() {
      return this.title.toUpperCase();
    }
  }
};
</script>

<style scoped>
.badge {
  background-color: #ccc;
  border-radius: 30px;
  padding: 0.5rem 1.5rem;
  display: inline-block;
  margin-right: 0.5rem;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  font-size: 0.6rem;
}

.frontend {
  background-color: #a4cff3;
  color: #000;
}

.backend {
  background-color: #4da1e8;
  color: #000;
}

.career {
  background-color: #81bdef;
  color: #000;
}
</style>
