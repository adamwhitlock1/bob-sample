<template>
  <div class="about">
    <h1>My name is {{ toTitleCase(name) }}</h1>
    <h1>{{ nameUpper }}</h1>
    <h1>{{ funk }}</h1>
    <input type="text" v-model="name" />
    <h1>{{ total }}</h1>
    <button @click="increment">add</button>
    <button @click="decrement">minus</button>
  </div>
</template>

<script>
import nameUtils from "@/name";
export default {
  data() {
    return {
      name: this.toTitleCase("funky chicken"),
      nameUpper: nameUtils.upper("adam"),
      funk: nameUtils.funk,
      total: 0,
    };
  },
  methods: {
    increment() {
      this.total++;
    },
    decrement() {
      this.total--;
      this.alertTotal();
    },
    alertTotal() {
      alert(this.total);
    },
    toTitleCase(str) {
      return str.replace(/\w\S*/g, function (txt) {
        return txt.charAt(0).toUpperCase() + txt.substr(1).toLowerCase();
      });
    },
  },
};
</script>
