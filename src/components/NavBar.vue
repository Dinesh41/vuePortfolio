<template>
  <nav class="box" ref="nav_bar">
    <div class="navbar-toggle" @click="isNavBarOpen = !isNavBarOpen">
      <i class="fas fa-bars"></i>
    </div>
    <ul id="nav_menu" :class="{ isOpen: isNavBarOpen }">
      <li v-for="nav_item in nav_items" :key="nav_item.nav_name">
        <a :href="nav_item.nav_link">{{ nav_item.nav_name }}</a>
      </li>
    </ul>
  </nav>
</template>
<script>
import jQuery from "jquery";
const $ = jQuery;
window.$ = $;
export default {
  props: {
    nav_items: Array,
    default_nav_link: String
  },
  data() {
    return {
      isNavBarOpen: false
    };
  },
  mounted() {
    this.enableHighlightOnScroll("sdf");
  },
  methods: {
    enableHighlightOnScroll(listId) {
      listId;
      // Cache selectors
      var lastId,
        topMenu = $("#nav_menu"),
        topMenuHeight = topMenu.outerHeight() + 1,
        // All list items
        menuItems = topMenu.find("a"),
        // Anchors corresponding to menu items
        scrollItems = menuItems.map(function() {
          var item = $($(this).attr("href"));
          if (item.length) {
            return item;
          }
        });

      // Bind click handler to menu items
      // so we can get a fancy scroll animation
      menuItems.click(function(e) {
        var href = $(this).attr("href"),
          offsetTop =
            href === "#" ? 0 : $(href).offset().top - topMenuHeight + 1;
        $("html, body")
          .stop()
          .animate(
            {
              scrollTop: offsetTop
            },
            850
          );
        e.preventDefault();
      });

      // Bind to scroll
      $(window).scroll(function() {
        // Get container scroll position
        var fromTop = $(this).scrollTop() + topMenuHeight;

        // Get id of current scroll item
        var cur = scrollItems.map(function() {
          if ($(this).offset().top < fromTop) return this;
        });
        // Get the id of the current element
        cur = cur[cur.length - 1];
        var id = cur && cur.length ? cur[0].id : "";

        if (lastId !== id) {
          lastId = id;
          // Set/remove active class
          menuItems
            .parent()
            .removeClass("isActive")
            .end();
          $('a[href$="' + id + '"')
            .parent()
            .addClass("isActive");
        }
      });
    }
  }
};
</script>
<style scoped>
@import url("https://fonts.googleapis.com/css?family=Montserrat");
body {
  background-color: #fff;
}
@media screen and (min-width: 320px) {
  .navbar-toggle {
    position: absolute;
    top: 5px;
    right: 15px;
  }
  .fa-bars {
    font-size: 22px;
  }
  .box {
    width: 100%;
    min-height: 32px;
    background: #2e4a62;
    padding: 5px 0px 1px 0px;
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
    list-style: none;
    padding: 0;
    display: none;
  }
  ul > li {
    padding: 2px 0px;
  }

  a {
    color: inherit;
    text-decoration: none;
  }
  .isActive {
    color: #94ff92;
    font-size: 20px;
  }
  .isOpen {
    display: block;
  }
}
@media screen and (min-width: 768px) {
  .navbar-toggle {
    display: none;
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
}
</style>
