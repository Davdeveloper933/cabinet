<template>
    <div role="button" class="ui-btn">
      <slot />
    </div>
</template>

<script>
    export default {
        name: "UiButton"
    }
</script>

<style lang="scss" scoped>

  .ui-btn {
    display: inline-flex;
    justify-content: center;
    align-items: center;
    width: fit-content;
    background: #4276F6;
    border-radius: 8px;
    font-weight: 500;
    font-size: 15px;
    text-align: center;
    transition: .3s;
    padding: 11px 31px;
    &:hover {
      box-shadow: 0px 9px 24px rgba(66, 118, 246, 0.4);
    }
  }

</style>
