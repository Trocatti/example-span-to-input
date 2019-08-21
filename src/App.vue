<template>
  <div id="app" class="container">
    <input
      type="text"
      v-if="edit"
      v-model="valueLocal"
      @blur="edit = false;"
      @keyup.enter="edit = false;"
      v-focus
    >
    <h1 v-else @click="edit = true;">{{valueLocal}}</h1>
  </div>
</template>

<script>
export default {
  name: "app",

  data() {
    return {
      edit: false,
      valueLocal: "Span for input, when clicking here!"
    };
  },

  watch: {
    value: function(oldValue, newValue) {
      this.valueLocal = newValue;
    }
  },

  directives: {
    focus: {
      inserted(el) {
        el.focus();
      }
    }
  }
};
</script>

<style scoped>
html,
body {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.container {
  margin: 50px;
}

input {
  border-radius: 3px;
  border: 1px solid #ddd;
  padding: 5px;
  box-shadow: 0px 0px 5px #adadad;
  width: 300px;
}
</style>
