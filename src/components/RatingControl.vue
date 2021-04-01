<template>
  <ul>
    <li :class="{ active: activeOption === 'poor' }" @click="activate('poor')">
      <button type="button">Poor</button>
    </li>
    <li
      :class="{ active: activeOption === 'average' }"
      @click="activate('average')"
    >
      <button type="button">Average</button>
    </li>
    <li
      :class="{ active: activeOption === 'great' }"
      @click="activate('great')"
    >
      <button type="button">Great</button>
    </li>
  </ul>
</template>

<script>
export default {
  props: ['modelValue'],
  emits: ['update:modelValue'],
  data() {
    return {
      activeOption: this.modelValue,
    };
  },

  methods: {
    activate(option) {
      this.activeOption = option;
      this.$emit('update:modelValue', option);
    },
  },
};
</script>

<style scoped>
.active {
  border-color: purple;
}

.active button {
  border-color: purple;
}
ul {
  list-style: none;
  margin: 0.5rem 0;
  padding: 0;
  display: flex;
}

li {
  margin: 0 1rem;
  display: flex;
  border: 1px solid #ccc;
  padding: 1rem;
  justify-content: center;
  align-items: center;
}

button {
  font: inherit;
  border: none;
  background-color: transparent;
  cursor: pointer;
}
</style>