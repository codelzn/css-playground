<template>
  <div class="sk01">
    <div class="shell">
      <input
        v-for="i in 5"
        :key="i"
        type="radio"
        name="position"
        :checked="i === 3"
      />
      <div class="box">
        <div v-for="i in 5" :key="i" class="item"></div>
      </div>
    </div>
  </div>
</template>
<style scoped lang="scss">
.sk01 {
  width: 100%;
  display: grid;
  place-items: center;
  height: 100vh;
  background: linear-gradient(to right, #f0b5cf 0%, #b7b5ff 100%);

  .shell {
    display: grid;
    align-items: center;
    grid-template-rows: 500px 200px;

    input {
      width: 35px;
      height: 35px;
      margin: 10px;

      @for $i from 1 through 5 {
        &:nth-of-type(#{$i}) {
          grid-column: #{$i + 1} / #{$i + 2};
          grid-row: 2 / 3;

          &:checked ~ .box {
            --position: #{$i};
          }
        }
      }
    }

    .box {
      grid-row: 1 / 2;
      grid-column: 1 / 8;
      width: 100vw;
      height: 570px;
      display: flex;
      justify-content: center;
      align-items: center;
      overflow: hidden;
      transform-style: preserve-3d;
      perspective: 800px;
      --middle: 3;
      --position: 1;

      @for $i from 1 through 5 {
        & .item:nth-of-type(#{$i}) {
          --offset: #{$i};
          background: url("https://picsum.photos/350/500?random=#{$i}");
        }
      }

      & .item {
        position: absolute;
        width: 350px;
        height: 500px;
        background-color: coral;
        --r: calc(var(--position) - var(--offset));
        --abs: max(calc(var(--r) * -1), var(--r));
        transition: all 0.25s linear;
        transform: rotateY(calc(-10deg * var(--r)))
          translateX(calc(-380px * var(--r)));
        z-index: calc(var(--position) - var(--abs));
        background-size: cover;
        box-shadow: 0 0 30px rgba(0, 0, 0, 0.6);
        border: 10px solid #b5c5ff;
      }
    }
  }
}
</style>
