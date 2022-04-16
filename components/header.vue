<template>
    <div class="header">
      <div class="wrapper">
        <a href="#" class="logo">
          Capella Finance
        </a>
        <div class="right-block">
<!--          <div class="flex-wrapper">-->
            <div v-if="false" class="select-lang">
              <select  role="button" name="" id="">
                <option value="en">ENG</option>
                <option value="en">RUS</option>
              </select>
            </div>
            <ui-select
              :options="options"
              :default="'ENG'"
              class="select select-lang"
              @input="onInput($event)"
            >

            </ui-select>
            <div class="buttons">
              <nuxt-link to="signin">
                <ui-button class="sign-in-btn">Sign In</ui-button>
              </nuxt-link>
              <nuxt-link to="signup">
              <ui-button @click="$emit('sign-up')" class="sign-up-btn">Sign Up</ui-button>
              </nuxt-link>
            </div>
<!--          </div>-->
        </div>
      </div>
    </div>
</template>

<script>
    import UiButton from "~/components/ui/ui-button.global";
    import UiSelect from "~/components/ui/ui-select.global";
    export default {
        name: "SiteHeader",
      components: {UiSelect, UiButton},
      data () {
          return {
            options: [
              'ENG',
              'RUS'
            ]
          }
      },
      methods: {
          onInput (event) {
            console.log('you selected',event)
          }
      }
    }
</script>

<style lang="scss" scoped>

  .header {
    .logo {
      font-weight: 600;
      font-size: 18px;
      white-space: nowrap;
    }
    .wrapper {
      display: flex;
      align-items: baseline;
      padding-top: 26px;
    }
    .right-block {
      padding-bottom: 13px;
      border-bottom: 1px solid #343841;
      display: flex;
      align-items: center;
      justify-content: space-between;
      width: 100%;
      margin-left: 80px;
    }
    .sign-in-btn {
      background: transparent !important;
      &:hover {
        box-shadow: unset;
      }
    }
    .select-lang {
      color: #787B89;
    }
  }

</style>
