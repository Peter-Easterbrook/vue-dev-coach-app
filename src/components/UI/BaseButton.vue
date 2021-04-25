<template>
  <button v-if="!link" :class="mode">
    <slot></slot>
  </button>
  <router-link v-else :to="to" :class="mode">
    <slot></slot>
  </router-link>
</template>

<script>
export default {
  props: {
    mode: {
      type: String,
      required: false,
      default: null
    },
    link: {
      type: Boolean,
      required: false,
      default: false
    },
    to: {
      type: String,
      required: false,
      default: '/'
    }
  }
};
</script>

<style scoped>
button,
a {
  text-decoration: none;
  padding: 0.75rem 1.5rem;
  font: inherit;
  background-color: #0a3252;
  border: 1px solid #0a3252;

  color: white;
  cursor: pointer;
  border-radius: 30px;
  margin-right: 0.5rem;
  display: inline-block;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
}

a:hover,
a:active,
button:hover,
button:active {
  background-color: #1c85de;
  border-color: #1c85de;
}

.flat {
  background-color: transparent;
  color: #1c85de;
  border: none;
}

.outline {
  background-color: transparent;
  border-color: #0a3252;
  color: #0a3252;
}

.flat:hover,
.flat:active,
.outline:hover,
.outline:active {
  background-color: #d7eafa;
}
</style>
