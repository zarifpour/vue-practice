<template>
  <div>{{ greet }} {{ name }}</div>
  <div v-html="username"></div>
  <div v-html="hack"></div>
  <h2 v-bind:id="headingId">Heading</h2>
  <button v-bind:disabled="isDisabled">Bind</button>
  <h2 class="underline">Underlined text</h2>
  <h2 class="underline" v-bind:class="status">Status</h2>
  <h2 v-bind:class="isPromoted && 'promoted'">Promoted Movie</h2>
  <h2 v-bind:class="isSoldout ? 'sold-out' : 'new'">Sold Out? Movie</h2>
  <h2 v-bind:class="['new', 'promoted']">Newly Promoted Movie</h2>
  <h2 v-bind:class="[isPromoted && 'promoted', isSoldout ? 'sold-out' : 'new']">
    Array Conditional Movie
  </h2>
  <h2
    v-bind:class="{
      promoted: isPromoted,
      new: !isSoldout,
      'sold-out': isSoldout,
    }"
  >
    Object Conditional Movie
  </h2>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      greet: "Howdy",
      name: "Daniel",
      username: "<b>zarif</b>",
      hack: `<a href="#" onclick="alert('You have been hacked!')">Win a prize!</a>`,
      headingId: "heading",
      isDisabled: false,
      status: "success",
      isPromoted: true,
      isSoldout: true,
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.underline {
  text-decoration: underline;
}

.promoted {
  font-style: italic;
}

.new {
  color: olivedrab;
}

.sold-out {
  color: red;
}
</style>
