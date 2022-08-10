<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <button v-on:click="addLink">add Link</button>
    <h2>{{externalLinks.title}}</h2>
    <ul>
      <li v-for="link in externalLinks.links" :key="link.id">
        <a
          :href="link.href"
          :target="link.target"
        >
        {{ link.text }}</a>
      </li>
    </ul>
    <h2>{{ecosystem.title}}</h2>
    <ul>
      <li v-for="link in ecosystem.links" :key="link.id">
        <a
          :href="link.href"
          :target="link.target"
        >
          {{ link.text }}</a>
      </li>

    </ul>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      msg: 'Welcome to Your Vue.js App',
      externalLinks: {
        title: 'Essential Links',
        links: [
          {
            id: 1,
            href: 'https://vuejs.org',
            target: '_blank',
            text: 'Core Docs',
          },
          {
            id: 2,
            href: 'https://forum.vuejs.org',
            target: '_blank',
            text: 'Forum',
          },
          {
            id: 3,
            href: 'https://chat.vuejs.org',
            target: '_blank',
            text: 'Community Chat',
          },
          {
            id: 4,
            href: 'https://twitter.com/vuejs',
            target: '_blank',
            text: 'Twitter',
          },
          {
            id: 5,
            href: 'http://vuejs-templates.github.io/webpack/',
            target: '_blank',
            text: 'Docs for This Template',
          },
        ],
      },
      ecosystem: {
        title: 'Ecosystem',
        links: [
          {
            id: 1,
            href: 'http://router.vuejs.org',
            target: '_blank',
            text: 'vue-router',
          },
          {
            id: 2,
            href: 'http://vuex.vuejs.org/',
            target: '_blank',
            text: 'vuex',
          },
          {
            id: 3,
            href: 'http://vue-loader.vuejs.org/',
            target: '_blank',
            text: 'vue-loader',
          },
          {
            id: 4,
            href: 'https://github.com/vuejs/awesome-vue',
            target: '_blank',
            text: 'awesome-vue',
          },
        ],
      },
    };
  },
  methods: {
    addLink() {
      this.externalLinks.links.push(
        {
          id: this.externalLinks.links.length + 1,
          text: 'test',
          href: '#',
          target: '',
        },
      );
    },
    //
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
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
