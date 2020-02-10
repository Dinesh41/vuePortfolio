<template>
  <div class="box" ref="nav_bar">
    <ul id="nav_menu">
      <li
        v-for="nav_item in nav_items"
        :key="nav_item.nav_name"
        :class="{ isActive: currentActiveRoute == nav_item.nav_link }"
      >
        <a :href="nav_item.nav_link">{{ nav_item.nav_name }}</a>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  props: {
    nav_items: Array,
    default_nav_link: String
  },
  data() {
    return {
      currentActiveRoute: ""
    };
  },
  mounted() {
    this.markActiveItemInNavBar();
    window.onscroll = function() {
      console.log(this.scrollTop());
    };
    window.onhashchange = () => {
      this.markActiveItemInNavBar();
    };
  },
  methods: {
    markActiveItemInNavBar() {
      let routeStartIndex = window.location.href.indexOf("#");
      if (routeStartIndex == -1) {
        this.currentActiveRoute = this.default_nav_link;
        return;
      }
      let currentRoute = window.location.href.substring(routeStartIndex);
      this.currentActiveRoute = currentRoute;
    }
  }
};
</script>
<style scoped>
@import url("https://fonts.googleapis.com/css?family=Montserrat");
body {
  background-color: #fff;
}

.box {
  width: 80%;
  margin: 0px auto;
  padding: 2px;
  background: #2e4a62;
  border-radius: 4px;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
  line-height: 20px;
  font-family: "Montserrat", sans-serif;
  color: #fff;
  z-index: 10;
  position: sticky;
  top: 0px;
}
ul {
  display: flex;
  list-style: none;
  justify-content: flex-end;
}
ul > li {
  padding: 0px 7px;
  margin: 0;
}

a {
  color: inherit;
  text-decoration: none;
}
.isActive {
  color: #94ff92;
  font-size: 20px;
}
</style>
