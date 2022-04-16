<template>
  <div class="custom-select" :tabindex="tabindex" @blur="open = false">
    <div class="selected" :class="{ open: open }" @click="open = !open">
      {{ selected }}
    </div>
    <div class="items" :class="{ selectHide: !open }">
      <div
        v-for="(option, i) of options"
        :key="i"
        @click="
          selected = option;
          open = false;
          $emit('input', option);
        "
      >
        {{ option }}
      </div>
    </div>
  </div>
</template>

<script>
    export default {
        name: "UiSelect",
      props: {
        options: {
          type: Array,
          required: true,
        },
        default: {
          type: String,
          required: false,
          default: null,
        },
        tabindex: {
          type: Number,
          required: false,
          default: 0,
        },
      },
      data() {
        return {
          selected: this.default
            ? this.default
            : this.options.length > 0
              ? this.options[0]
              : null,
          open: false,
        };
      },
      mounted() {
        this.$emit("input", this.selected);
      },
    }
</script>

<style lang="scss" scoped>
  .custom-select {
    position: relative;
    text-align: left;
    outline: none;
  }

  .custom-select .selected {
    background-color: transparent;
    color: inherit;
    cursor: pointer;
    user-select: none;
    padding: 10px 10px 10px 0;
    transition: .3s;
  }

  .custom-select .selected.open {

  }

  .custom-select .selected:after {
    position: absolute;
    content: "\276E";
    transform: rotate(-90deg);
    display: inline-block;
    left: 3.5vw;
    top: 8px;
    font-size: 2vh;
  }

  .custom-select .items {
    color: inherit;
    overflow: hidden;
    position: absolute;
    background: #232630;
    left: 0;
    right: 0;
    z-index: 1;
  }

  .custom-select .items div {
    color: inherit;
    cursor: pointer;
    user-select: none;
    padding: 10px 10px 10px 0;
  }

  .custom-select .items div:hover {
    color: #ffffff;
  }

  .selectHide {
    display: none;
  }
</style>
