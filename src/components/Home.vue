<template>
  <div class="container">
      <h1 class="dinner">What's for dinner?</h1>
      <button v-on:click="getMeal" class="feed-me">Feed me!</button>
      <p id="meal"></p>
  </div>
</template>

<script>

export default {
  name: 'Home',
  methods: {
    getMeal: function () {
      var myMeals = ['Pizza', 'Quiche', 'Noodles', 'Salad', 'Rice with meatballs', 'Chili sin carne']
      var mealNumber = Math.floor(Math.random() * myMeals.length)
      document.getElementById('meal').textContent = myMeals[mealNumber]
    }
  }
}
</script>

<style lang="scss">
@import 'src/assets/scss/main.scss';

body {
    background: $purple;
}

.container {
    max-width: 320px;
    margin: 0 auto;
    text-align: center;

    .dinner {
        color: $pink;
        font-size: 2em;
        margin-top: 15vh;
    }

    .feed-me {
        background: $white;
        border-bottom: 5px solid $grey;
        border-radius: 8px;
        padding: 10px 30px;
        margin: 1em;
        color: $darkgrey;
        height: 45px;
        text-decoration: none;
        outline: 0;
        transition: all 0.1s;
        font-size: 16px;
        -webkit-transition: all 0.1s;
        &:active {
            transform: translate(0px, 5px);
            -webkit-transform: translate(0px, 5px);
            border-bottom: 1px solid;
        }
    }

    #meal {
        color: $white;
        font-size: 1.5em;
    }
}
</style>
