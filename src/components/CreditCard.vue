<template>
	<vue-flip
		:active-hover = "true"
		width					= "500px"
		height				= "300px"
	>
		<template v-slot:front>
      <div
        class  = "front-side"
        :style = "{ background: gradient }"
      >
        <div class = "ellipse" :style = "{ background: gradient }"></div>
        <div class = "ellipse ellipse--below" :style = "{ background: gradient }"></div>

        <div class = "top">
          <div class = "balance">
            <p class = "balance-name">Current Balance</p>
            <p class = "balance-value">$5,750,20</p>
          </div>
          <div class = "mastercard">
            <img src = "@/assets/img/master-card.png" alt = "mastercard">
            <p class = "mastercard__text">mastercard</p>
          </div>
        </div>
        <div class = "bottom">
          <p>5282 3456 7890 1289</p>
          <p>09/25</p>
        </div>

        <div class = "ellipse ellipse--bottom" :style = "{ background: gradient }"></div>
      </div>
		</template>
		<template v-slot:back >
      <div
        class  = "back-side"
        :style = "{ background: gradient }"
      >
        <div class = "back-side__black-line"></div>
        <div class = "back-side__content">
          <div class = "back-side__container-left">
            <div class = "cvv">123</div>
            <p class = "lil-text">AUTHORIZED SIGNATURE</p>
            <div class = "bank">
              <p>BANK</p>
              <div></div>
              <div></div>
              <div></div>
              <div></div>
            </div>
            <p class = "lil-text">
              All data is fictitious and not suitable for use.
            </p>
          </div>
          <div class = "back-side__container-right">
            <a href = "https://github.com/RyzenRanger" target = "_blank">
              <img src="https://avatars.githubusercontent.com/RyzenRanger" alt="RyzenRanger">
            </a>
          </div>
        </div>
      </div>
		</template>
	</vue-flip>
</template>

<script>
import VueFlip from 'vue-flip';

export default {
	name: 'credit-card',

	components: { 'vue-flip': VueFlip },

  props: {
    randomColors: {
      type: Object,
      required: true
    }
  },

  computed: {
    gradient () {
      if (this.randomColors?.first && this.randomColors?.second) {
        return `linear-gradient(177.23deg,
                rgba(${this.randomColors.first.r}, ${this.randomColors.first.g}, ${this.randomColors.first.b}, 0.6),
                rgba(${this.randomColors.second.r}, ${this.randomColors.second.g}, ${this.randomColors.second.b}, 0.6) 109.75%)`
      }
      return 'linear-gradient(177.23deg, rgba(154, 29, 250, 0.6), rgba(58, 73, 249, 0.6) 109.75%)'
    },
  }
}
</script>

<style lang = 'scss'>
$color-text: #FFFFFF;

.flip-container { // default class for vue-flip
  margin-bottom: 20px;
}

.front-side,
.back-side {
	border-radius: 30px;
	width: 500px;
	height: 300px;
  overflow: hidden;
	box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
  filter: drop-shadow(0px 4px 4px rgba(0, 0, 0, 0.25));
}

.front-side {
  position: relative;
  padding: 0 30px 30px 30px;
  display: flex; flex-direction: column; justify-content: space-between;
  color: $color-text;
  .top {
    display: flex; justify-content: space-between;

    .balance {
      padding-top: 30px;
      font-size: 40px;
      font-weight: 500;
      &-name {
        font-size: 28px;
        opacity: 0.6;
        margin-bottom: 10px;
      }
    }

    .mastercard {
      position: relative;
      &__text {
        position: absolute;
        top: 80px;
        left: 6px;
      }
    }
  }

  .bottom {
    display: flex; justify-content: space-between;
    font-size: 24px;
    letter-spacing: 0.1rem;
  }

  .ellipse {
    z-index: -1;
    position: absolute;
    top: -55px;
    right: -140px;
    width: 350px;
    height: 200px;
    border-radius: 50%;

    &--below {
      top: 0px;
    }

    &--bottom {
      top: 190px;
      left: -30px;
    }
  }
}

.back-side {
  padding-top: 25px;

  &__black-line {
    width: 100%;
    height: 60px;
    background: rgba(0, 0, 0, 0.5);
    margin-bottom: 20px;
  }

  &__content {
    display: flex;
  }

  &__container-left {
    width: 60%;
    padding: 0 20px 20px 20px;
    color: $color-text;

    .cvv {
      font-size: 26px;
      border-radius: 10px;
      padding: 5px 10px;
      width: 100%;
      text-align: right;
      color: black;
      background-color: rgba(255, 255, 255, 0.5);
      margin-bottom: 5px;
    }

    .lil-text {
      font-size: 12px;
      margin-bottom: 60px;
    }

    .bank {
      display: flex;
      align-items: center;
      p {
        font-size: 30px;
        margin-right: 10px;
      }
      div {
        margin-right: 3px;
        width: 20px; height: 20px;
        background-color: #FFFFFF;
        border-radius: 50%;
      }
    }
  }

  &__container-right {
    width: 40%;
    img {
      width: 90%;
      border-radius: 50%;
      transition: 0.5s;

      &:hover {
        box-shadow: 0px 10px 10px rgba(0, 0, 0, 1);
      }
    }
  }
}
</style>
