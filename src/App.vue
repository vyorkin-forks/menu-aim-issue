<template>
  <div>
  <ul class="menu-aim">
        <li class="menu-aim__item">
          <a class="menu-aim__item-name" href="#">foo</a>
          <ul class="menu-aim__item-submenu">
            <li><a href="#">qux</a></li>
            <li><a href="#">quux</a></li>
            <li><a href="#">quuux</a></li>
            <li><a href="#">quuuux</a></li>
            <li><a href="#">quuuuux</a></li>
            <li><a href="#">quuuuuux</a></li>
            <li><a href="#">quuuuuuux</a></li>
          </ul>
        </li>
        <li class="menu-aim__item">
          <a class="menu-aim__item-name" href="#">bar</a>
          <ul class="menu-aim__item-submenu">
            <li><a href="#">baz</a></li>
            <li><a href="#">qux</a></li>
          </ul>
        </li>
      </ul>
  </div>
</template>

<script>
import menuAim from 'menu-aim/src'
export default {
  mounted () {
    menuAim(document.querySelector('.menu-aim'), {
      contentDirection: 'right',
      menuItemSelector: '.menu-aim__item',
      menuItemActiveClassName: 'menu-aim__item--active',
      delayingClassName: 'menu-aim--delaying'
    })
  }
}
</script>

<style>
li {
  list-style: none;
}
a {
  text-decoration: none;
}
.menu-aim {
  width: 300px;
}
.menu-aim__item {
  position: relative;
  width: 300px;
}
.menu-aim a {
  display: block;
  color: blue;
}
.menu-aim a:hover,
.menu-aim__item--active .menu-aim__item-name {
  color: white;
  background: blue;
}
.menu-aim--delaying .menu-aim__item-name:hover {
  color: blue;
  background: none;
}
.menu-aim__item-submenu {
  display: none;
  position: absolute;
  top: 0;
  left: 300px;
  width: 300px;
}
.menu-aim__item--active .menu-aim__item-submenu {
  display: block;
}
</style>