<template>
  <div class="topnav">
    <div class="logo">
      <div class="icon">
        <use xlink:href="#icon-king"></use>
      </div>
    </div>
    <ul class="menu">
      <li>
        <router-link to='/doc'>文档</router-link>
      </li>
    </ul>
    <span
      class="toggleAside"
      @click="toggleMenu"
    ></span>
  </div>
</template>

<script lang="ts">
import { Ref, inject } from "vue";
export default {
  name: "TopNav",
  setup() {
    const menuVisible = inject<Ref<Boolean>>("menuVisible");
    const toggleMenu = () => {
      menuVisible.value = !menuVisible.value;
    };

    return { toggleMenu };
  },
};
</script>

<style lang="scss" scoped>
$color: #007974;
.topnav {
  display: flex;
  justify-content: center;
  align-items: center;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 10;
  padding: 16px;
  color: $color;

  > .logo {
    margin-right: auto;
    max-width: 6em;

    > svg {
      width: 32px;
      height: 32px;
    }
  }

  > .menu {
    display: flex;
    flex-wrap: nowrap;
    white-space: nowrap;

    > li {
      margin: 0 1em;
    }
  }

  > .toggleAside {
    display: none;
    position: absolute;
    left: 16px;
    top: 50%;
    transform: translateY(-50%);
    width: 24px;
    height: 24px;
    background: red;
  }

  @media (max-width: 500px) {
    > .menu {
      display: none;
    }
    > .logo {
      margin: 0 auto;
    }
    > .toggleAside {
      display: inline-block;
    }
  }
}
</style>