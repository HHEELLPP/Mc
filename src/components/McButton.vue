<template>
  <button class="btn" type="button" @click="$emit('click')">
    <span><slot></slot></span>
  </button>
</template>

<script>
export default {
  name: "McButton",
};
</script>

<style lang="scss">
.btn {
  align-items: stretch;
  background-color: var(--color-btn-bg);
  border: 1px solid #1b1b1b;
  color: var(--color-on-btn);
  cursor: pointer;
  display: flex;
  font-size: 0.825rem;
  font-weight: normal;
  justify-content: space-around;
  position: relative;
  padding: 0;
  text-align: center;
  transition-property: background-color, border-color, box-shadow;
  transition-duration: 0.35s;
  transition-timing-function: cubic-bezier(0.25, 0.46, 0.45, 0.94);

  &:hover,
  &:focus,
  &:active {
    --shadow-color: #464747;
    background-color: #313234;
    border-bottom-width: 0;
    border-top-width: 2px;
  }

  & > span {
    align-items: center;
    border-bottom: 3px solid #313233;
    box-shadow: inset 0 0 1px 2px var(--shadow-color, #6a6c70);
    box-sizing: border-box;
    display: flex;
    flex: 1 1;
    flex-flow: row nowrap;
    justify-content: space-around;
    padding: calc(2 * var(--size-base)) calc(4 * var(--size-base));
    text-align: center;
    user-select: none;
  }

  &:active > span::after,
  &.active > span::after {
    background-color: white;
    bottom: 2px;
    content: "";
    height: 2px;
    left: 50%;
    position: absolute;
    transform: translateX(-50%);
    width: 75%;
    z-index: 50;
  }
}
</style>