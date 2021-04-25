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
  color: #252525;
  border-radius: 30px;
  padding: 0.5rem 1.5rem;
  display: inline-block;
  margin-right: 0.5rem;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
}

.frontend {
  background-color: #1870bb;
  color: #f7f7f7;
}

.backend {
  background-color: #4da1e8;
  color: #f7f7f7;
}

.career {
  background-color: #81bdef;
  color: #f7f7f7;
}
</style>
