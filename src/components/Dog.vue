<template>
  <div>
    <button @click="getDog">GET a {{ breed }}</button>
    <img :src="dog.message" />
  </div>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Dog",
  props: {
    breed: String,
  },
  data() {
    return {
      dog: "",
    };
  },
  methods: {
    getDog: async function () {
      const response = await fetch(
        `https://dog.ceo/api/breed/${this.breed}/images/random`
      );
      this.dog = await response.json();
    },
  },
};
</script>

<style scoped></style>
