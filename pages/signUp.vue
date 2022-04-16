<template>
    <div class="sign-up">
      <div class="container">
        <div class="main-block">
          <div class="content">
            <h2 class="main-title">Sign Up</h2>
            <div class="custom-wrapper form sign-in-form">
              <h3 class="title">Enter Email</h3>
              <div class="email-wrap">
                <input type="email" placeholder="Your Email">
                <ui-button class="arrow-right">
                  <img src="assets/img/arrow-right.png" alt="">
                </ui-button>
              </div>
            </div>
            <div v-if="false" class="custom-wrapper form sign-up-form">
              <h3 class="title">Enter Email</h3>
              <div class="email-wrap">
                <input type="email" placeholder="Your Email">
              </div>
              <h3 class="title" style="margin-top: 11px">Enter Password</h3>
              <div class="email-wrap">
                <input type="password" placeholder="Your Password">
              </div>
              <ui-button class="wallet-btn sign-up-btn">
                Sign Up
              </ui-button>
            </div>
            <div class="line"></div>
            <div class="custom-wrapper wallet-connect">
              <h3 class="title">Or Connect your Wallet</h3>
              <ui-button class="wallet-btn">
                Connect Wallet
              </ui-button>
            </div>
            <div class="line"></div>
            <div class="custom-wrapper continue-with">
              <h3 class="title">Or Continue With</h3>
              <div class="socials">
                <a class="social-item" href="#" :style="{backgroundColor: item.bg}" v-for="(item,indx) in socials" :key="indx">
                  <img :src="`assets/img/${item.img}`" alt="">
                </a>
              </div>
            </div>
          </div>
          <div class="terms">
          <a href="#" class="terms-text">
            Term of service
          </a>
          </div>
        </div>
      </div>
    </div>
</template>

<script>
    import UiButton from "~/components/ui/ui-button.global";
    export default {
        name: "signUpPage",
      layout: "DefaultLayout",
      components: {UiButton},
      data () {
          return {
            showSignUp: false,
            socials: [
              {
                img:"fb-icon.svg",
                bg: "#3B5998"
              },
              {
                img:"google-icon.svg",
                bg: "#FFFFFF"
              },
              {
                img:"twitter-icon.svg",
                bg: "#55ACEE"
              },
              {
                img:"apple-icon.svg",
                bg: "#FFFFFF"
              }
            ]
          }
      },
      methods: {
          signUp() {
            this.showSignUp = true
          },
        signIn() {
          this.showSignUp = false
        }
      }
    }
</script>

<style lang="scss" scoped>

  .sign-up {
    .main-block {
      width: 100%;
      display: flex;
      align-items: center;
      flex-direction: column;
      justify-content: space-between;
    }
    .content {
      margin-top: 74px;
      padding-bottom: 176px;
    }
    .custom-wrapper {
      background: #1C2027;
      border-radius: 10px;
      padding: 25px;
      margin-bottom: 17px;
      margin-top: 17px;
      .title {
        font-size: 12px;
        line-height: 15px;
        color: #787B89;
        margin-bottom: 7px;
      }
    }
    .main-title {
      font-family: 'TT Commons',sans-serif;
      font-weight: 400;
      font-size: 30px;
      text-align: center;
    }
    .terms {
      padding-bottom: 26px;
      &-text {
        font-size: 16px;
        text-decoration-line: underline;
        color: #787B89;
      }
    }
    .custom-wrapper.form {
      margin-top: 40px;
    }

    .custom-wrapper.sign-up-form {
      input {
        padding-bottom: 12px;
        padding-top: 12px;
      }
    }
    .arrow-right {
      padding: 10px;
      border-radius: 4px;
    }
    .email-wrap {
      width: 100%;
      border: 1px solid #343841;
      border-radius: 6px;
      display: flex;
      padding: 3px 3px 3px 15px;
      align-items: center;
    }
    input {
      width: 100%;
      height: 100%;
      background: rgba(0,0,0,0);
    }
    .wallet-connect {
      .wallet-btn {
        width: 100%;
        padding: 15px 31px;
      }
    }
    .line {
      background: #343841;
      height: 1px;
    }
    .socials {
      display: grid;
      grid-template-columns: repeat(4,73px);
      grid-column-gap: 12px;
      .social-item {
        border-radius: 10px;
        display: flex;
        justify-content: center;
        align-items: center;
        padding: 18px;
        height: 50px;
      }
    }

    input:-webkit-autofill,
    input:-webkit-autofill:hover,
    input:-webkit-autofill:focus {
      -webkit-text-fill-color: white;
      -webkit-box-shadow: 0 0 0px 1000px #1C2027 inset;
      transition: background-color 5000s ease-in-out 0s;
    }
    .sign-up-btn {
      width: 100%;
      margin-top: 21px;
      padding: 15px 31px;
    }
  }

</style>
