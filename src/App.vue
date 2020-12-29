<template>
  <div class="game">
    <div class="game__container">
      <h2 class="game__title">Получи свою карту Хвоха</h2>
      <div class="game__img-container">
        <img :src="value" alt="" />
      </div>
      <button class="game__button" type="button" @click="randomImage">
        Next
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",

  data() {
    return {
      value: String,
      arrayNumberImage: [1],
    };
  },

  mounted() {
    this.value = require(`./assets/img/${1}.jpg`);
  },

  methods: {
    randomImage() {
      console.log(this.arrayNumberImage);
      const numberValue = Math.floor(Math.random() * 69 + 1);
      const newValue = require(`./assets/img/${numberValue}.jpg`);
      this.value = newValue;
    },
  },
};
</script>

<style lang="scss">
body {
  background: linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #23d5ab);
  background-size: 400% 400%;
  -webkit-animation: Gradient 15s ease infinite;
  -moz-animation: Gradient 15s ease infinite;
  animation: Gradient 15s ease infinite;
}

@-webkit-keyframes Gradient {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}

@-moz-keyframes Gradient {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}

@keyframes Gradient {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}

* {
  box-sizing: border-box;
}

ul {
  padding: 0;
  margin: 0;
  list-style: none;
}

h1,
h2,
h3,
h4,
h5,
h6 {
  font-weight: normal;
  margin: 0;
}

p {
  margin: 0;
  padding: 0;
}

button {
  appearance: none;
  outline: none;
  border: 0;
  border-radius: 0;
  padding: 0;
  box-shadow: none;
  text-decoration: none;
  background: none;
  cursor: pointer;
}

a {
  color: inherit;
  cursor: pointer;
  text-decoration: none;
}

img,
source {
  display: block;
  max-width: 100%;
  max-height: 100%;
}

svg {
  display: block;
  width: 100%;
  height: auto;
}

.game {
  &__container {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin: 0 auto;
    width: 90%;
  }

  &__title {
    margin-top: 10%;
    margin-bottom: 10%;
    font-size: 20px;
    text-transform: uppercase;
    color: #ffffff;
  }

  &__img-container {
    width: 90%;
    border: 1px solid #000000;
    border-radius: 20px;
    overflow: hidden;
  }

  &__button {
    margin-top: 10%;
    width: 30%;
    height: 40px;
    border: 1px solid #ffffff;
    border-radius: 20px;
    font-weight: 600;
    text-transform: uppercase;
    outline: none;
    color: #ffffff;

    &:active {
      opacity: 0.5;
    }
  }
}
</style>
