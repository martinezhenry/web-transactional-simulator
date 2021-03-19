<template>
  <div>
    <li v-for="(link, index) in links" :key="index" :id="link.id">
      <ul v-if="link.parent > 0">
        <li>{{ link.text }}</li>
      </ul>
      <span v-else>{{ link.text }}</span>
    </li>
  </div>
</template>

<script>
export default {
  name: "MenuLinks",
  data() {
    return {
      links: [
        {
          text: "Home",
          id: 1,
          parent: -1,
        },
        {
          text: "Messages",
          id: 2,
          parent: -1,
        },
        {
          text: "Build",
          id: 3,
          parent: 2,
        },
      ],
    };
  },
  methods: {
    findParent(id) {
      var element = undefined;

      this.links.some(function (link) {
        console.log(id + " : " + link.id);
        if (link.id == id) {
          console.log("eya");
          element = link;
          return;
        }
      });
      return element;
    },
    buildSubMenu(parentId) {
      var parent = this.findParent(parentId);
      console.log(parent);
      return parent;
    },
  },
  computed: {},
};
</script>

<style lang="scss" scoped>
</style>
