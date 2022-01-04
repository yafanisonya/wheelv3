<template>
  <div class="demo">
    <h2>{{component.__sourceCodeTitle}}</h2>
    <div class="demo-component">
      <component :is="component" />
    </div>
    <div class="demo-actions">
      <Button>查看代码</Button>
    </div>
    <div class="demo-code">
      <pre
        class="language-html"
        v-html="Prism.highlight(component.__sourceCode,Prism.languages.html,'html')"
      />
    </div>
  </div>
</template>

<script lang="ts">
import Button from "../lib/Button.vue";
import "prismjs";
import "prismjs/themes/prism.css";
const Prism = (window as any).Prism;

export default {
  components: {
    Button,
  },
  props: {
    component: Object,
  },
  setup() {
    return {
      Prism,
    };
  },
};
</script>

<style lang="scss">
$border-color: #d9d9d9;

.demo {
  margin: 16px 0 32px;
  border: 1px solid $border-color;

  > h2 {
    padding: 8px 16px;
    font-size: 20px;
    border-bottom: 1px solid $border-color;
  }

  &-component {
    padding: 16px;
  }

  &-actions {
    padding: 8px 16px;
    border-top: 1px dashed $border-color;
  }

  &-code {
    padding: 8px 16px;
    border-top: 1px dashed $border-color;

    > pre {
      margin: 0;
      line-height: 1.1;
      font-family: Consolas, "Courier New", Courier, monospace;
    }
  }
}
</style>