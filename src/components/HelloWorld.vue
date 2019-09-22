<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      For a guide and recipes on how to configure / customize this project,
      <br />check out the
      <a
        href="https://cli.vuejs.org"
        target="_blank"
        rel="noopener"
      >vue-cli documentation</a>.
    </p>
    <h3>Installed CLI Plugins</h3>
    <ul>
      <li>
        <a
          href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-babel"
          target="_blank"
          rel="noopener"
        >babel</a>
      </li>
    </ul>
    <h3>Essential Links</h3>
    <ul>
      <li>
        <a href="https://vuejs.org" target="_blank" rel="noopener">Core Docs</a>
      </li>
      <li>
        <a href="https://forum.vuejs.org" target="_blank" rel="noopener">Forum</a>
      </li>
      <li>
        <a href="https://chat.vuejs.org" target="_blank" rel="noopener">Community Chat</a>
      </li>
      <li>
        <a href="https://twitter.com/vuejs" target="_blank" rel="noopener">Twitter</a>
      </li>
      <li>
        <a href="https://news.vuejs.org" target="_blank" rel="noopener">News</a>
      </li>
    </ul>
    <h3>Vega-lite</h3>
    <div id="vis"></div>
  </div>
</template>

<script>
import vegaEmbed from "vega-embed";
export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  data() {
    return {
      spec: {
        $schema: "https://vega.github.io/schema/vega-lite/v2.0.json",
        description: "A simple bar chart with embedded data.",
        data: {
          values: [
            { a: "A", b: 28 },
            { a: "B", b: 55 },
            { a: "C", b: 43 },
            { a: "D", b: 91 },
            { a: "E", b: 81 },
            { a: "F", b: 53 },
            { a: "G", b: 19 },
            { a: "H", b: 87 },
            { a: "I", b: 52 }
          ]
        },
        mark: "bar",
        encoding: {
          x: { field: "a", type: "ordinal" },
          y: { field: "b", type: "quantitative" }
        }
      }
    };
  },
  mounted() {
    vegaEmbed('#vis', this.spec)
    console.log('spec:', this.spec)
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
