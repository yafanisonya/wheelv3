<template>
  <button
    @click="toggle"
    :class="{checked: value}"
  >
    <span></span>
  </button>
</template>

<script lang="ts">
export default {
  props: {
    value: Boolean,
  },
  setup(props, context) {
    const toggle = () => {
      context.emit("update:value", !props.value);
      // context.emit("input", !props.value);
    };
    return { toggle };
  },
};
</script>

<style lang="scss" scoped>
$h: 22px;
$h2: $h - 4px;

button {
  position: relative;
  width: $h * 2;
  height: $h;
  border: none;
  background: grey;
  border-radius: $h/2;
}

span {
  position: absolute;
  top: 2px;
  left: 2px;
  width: $h2;
  height: $h2;
  border-radius: $h2/2;
  background: white;
  transition: left 250ms;
}

button.checked {
  background: blue;
}

button.checked > span {
  left: calc(100% - #{$h2} - 2px);
}

button:focus {
  outline: none;
}
</style>