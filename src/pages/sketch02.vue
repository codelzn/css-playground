<template>
  <div class="sk02">
    <div class="sk02_ctn">
      <div :class="isLogin ? 'is-txl' : null" class="ctn a-ctn">
        <form action="" class="form a-form">
          <h2 class="form_title title">新規取得</h2>
          <div class="form_icons flex">
            <img class="icon" src="/google.svg" alt="google" />
            <img class="icon" src="/amazon.svg" alt="amazon" />
            <img class="icon" src="/github.svg" alt="github" />
          </div>
          <span class="form_span">メールで新規取得</span>
          <input type="text" class="form_input" placeholder="ユーザーネーム" />
          <input type="text" class="form_input" placeholder="メールアドレス" />
          <input type="text" class="form_input" placeholder="パスワード" />
          <button class="form_button button submit" @click.prevent="null">
            新規取得
          </button>
        </form>
      </div>
      <div :class="isLogin ? 'is-txl is-z' : null" class="ctn b-ctn">
        <form action="" class="form b-form">
          <h2 class="form_title title">ログイン</h2>
          <div class="form_icons flex">
            <img class="icon" src="/google.svg" alt="google" />
            <img class="icon" src="/amazon.svg" alt="amazon" />
            <img class="icon" src="/github.svg" alt="github" />
          </div>
          <span class="form_span">メールで新規取得</span>
          <input type="text" class="form_input" placeholder="メールアドレス" />
          <input type="text" class="form_input" placeholder="パスワード" />
          <a href="#" class="form_link">ログインできない？</a>
          <button class="form_button button submit" @click.prevent="null">
            ログイン
          </button>
        </form>
      </div>
      <div :class="isLogin ? 'is-txr' : null" class="switch">
        <div :class="isLogin ? 'is-txr' : null" class="switch_circle"></div>
        <div
          :class="isLogin ? 'is-txr' : null"
          class="switch_circle switch_circle-t"
        ></div>
        <div :class="isLogin ? 'is-hidden' : null" class="switch_ctn">
          <h2 class="switch_title title">おかえり</h2>
          <p class="switch_description description">
            すでにアカウントお持ちでしょうか？
          </p>
          <button
            class="switch_button button switch-btn"
            @click="isLogin = !isLogin"
          >
            ログイン
          </button>
        </div>
        <div :class="isLogin ? null : 'is-hidden'" class="switch_ctn">
          <h2 class="switch_title title">こんにちは</h2>
          <p class="switch_description description">新規取得しませんか？</p>
          <button
            class="switch_button button switch-btn"
            @click="isLogin = !isLogin"
          >
            新規取得
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
const isLogin = ref(true);
</script>
<style lang="scss">
.sk02 {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  user-select: none;
  width: 100%;
  height: 100vh;
  display: grid;
  place-items: center;
  font-size: 12px;
  background: #ecf0f3;
  color: #a0a5a8;

  .sk02_ctn {
    position: relative;
    width: 1000px;
    height: 600px;
    min-width: 1000px;
    min-height: 600px;
    padding: 25px;
    background-color: #ecf0f3;
    box-shadow: 10px 10px 10px #d1d9e6, -10px -10px 10px #f9f9f9;
    border-radius: 12px;
    overflow: hidden;
  }

  @media screen and (max-width: 1200px) {
    .sk02_ctn {
      transform: scale(0.7);
    }
  }

  @media screen and (max-width: 1000px) {
    .sk02_ctn {
      transform: scale(0.6);
    }
  }

  @media screen and (max-width: 800px) {
    .sk02_ctn {
      transform: scale(0.5);
    }
  }

  @media screen and (max-width: 600px) {
    .sk02_ctn {
      transform: scale(0.4);
    }
  }

  .ctn {
    display: grid;
    place-items: center;
    position: absolute;
    top: 0;
    width: 600px;
    height: 100%;
    padding: 25px;
    background-color: #ecf0f3;
    transition: 1.25s;
  }

  .form {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    width: 100%;
    height: 100%;
  }

  .icon {
    margin: 0 5px;
    border: 2px solid rgba(0, 0, 0, 0.5);
    border-radius: 50%;
    width: 25px;
    height: 25px;
    padding: 3px;
    opacity: 0.5;
    transition: 0.1s;

    &:hover {
      opacity: 1;
      transition: 0.15s;
      cursor: pointer;
    }
  }

  .form_input {
    outline: none;
    width: 350px;
    height: 40px;
    margin: 4px 0;
    padding-left: 25px;
    font-size: 13px;
    letter-spacing: 0.15px;
    background-color: #ecf0f3;
    transition: 0.25s ease;
    border-radius: 8px;
    box-shadow: inset 2px 2px 4px #d1d9e6, inset -2px -2px 4px #f9f9f9;

    &:focus {
      box-shadow: inset 4px 4px 4px #d1d9e6, inset -4px -4px 4px #f9f9f9;
    }
  }

  .form_span {
    margin-top: 30px;
    margin-bottom: 12px;
  }

  .form_link {
    color: #181818;
    font-size: 15px;
    margin-top: 25px;
    border-bottom: 1px solid #a0a5a8;
    line-height: 2;
  }

  .title {
    font-size: 34px;
    font-weight: 700;
    line-height: 3;
    color: #181818;
    letter-spacing: 10px;
  }

  .description {
    font-size: 14px;
    line-height: 1.6;
    letter-spacing: 0.25px;
    text-align: center;
  }

  .button {
    outline: none;
    width: 180px;
    height: 50px;
    border-radius: 25px;
    margin-top: 50px;
    font-weight: 700;
    font-size: 14px;
    letter-spacing: 1.15px;
    background-color: #4b70e2;
    color: #f9f9f9;
    box-shadow: 8px 8px 16px #d1d9e6, -8px -8px 16px #f9f9f9;
  }

  .a-ctn {
    z-index: 100;
    left: calc(100% - 600px);
  }

  .b-ctn {
    left: calc(100% - 600px);
    z-index: 0;
  }

  .switch {
    display: flex;
    justify-content: center;
    align-items: center;
    position: absolute;
    top: 0;
    left: 0;
    height: 100%;
    width: 400px;
    padding: 50px;
    z-index: 200;
    transition: 1.25s;
    background-color: #ecf0f3;
    overflow: hidden;
    box-shadow: 4px 4px 10px #d1d9e6, -4px -4px 10px #d1d9e6;
  }

  .switch_circle {
    position: absolute;
    width: 500px;
    height: 500px;
    border-radius: 50%;
    background-color: #ecf0f3;
    box-shadow: inset 8px 8px 12px #b8b3c7, inset -8px -8px 12px #ffffff;
    bottom: -60%;
    left: -60%;
    transition: 1.25s;
  }

  .switch_circle-t {
    top: -30%;
    left: 60%;
    width: 300px;
    height: 300px;
  }

  .switch_ctn {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    position: absolute;
    width: 400px;
    padding: 50px 55px;
    transition: 1.25s;
  }

  .switch_button {
    cursor: pointer;

    &:active,
    &:focus {
      box-shadow: 2px 2px 6px #d1d9e6, -2px -2px 6px #f9f9f9;
      transform: scale(0.97);
      transition: 0.25s;
    }
  }

  .switch_button:hover,
  .submit:hover {
    box-shadow: 6px 6px 10px #d1d9e6, -6px -6px 10px #f9f9f9;
    transform: scale(0.985);
    transition: 0.25s;
  }

  .is-txr {
    left: calc(100% - 400px);
    transition: 1.25s;
    transform-origin: left;
  }

  .is-txl {
    left: 0;
    transition: 1.25s;
    transform-origin: right;
  }

  .is-z {
    z-index: 200;
    transition: 1.25s;
  }

  .is-hidden {
    visibility: hidden;
    opacity: 0;
    position: absolute;
    transition: 1.25s;
  }
}
</style>
