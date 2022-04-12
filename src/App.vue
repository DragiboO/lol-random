<template>
  <section>
    <div class="top">
      <h1>Chall-IA Random</h1>
    </div>

    <div class="game-setup">
      <div class="full-counter">
        <div class="btn green" @click="count_card--" v-if="count_card >= 3">
          <p>-</p>
        </div>
        <div class="btn red" v-if="count_card == 2">
          <p>Min</p>
        </div>

        <div class="counter">
          <p>{{ count_card }}</p>
        </div>

        <div class="btn green" @click="count_card++" v-if="count_card <= 5">
          <p>+</p>
        </div>
        <div class="btn red" v-if="count_card == 6">
          <p>Max</p>
        </div>
      </div>

      <div class="start">
        <p class="btn-start">Roll</p>
      </div>
    </div>

    <div class="all-card">

      <div class="card first"></div>
      <div class="card second"></div>
      <div class="card third" v-if="count_card >= 3"></div>
      <div class="card fourth" v-if="count_card >= 4"></div>
      <div class="card fifth" v-if="count_card >= 5"></div>
      <div class="card sixth" v-if="count_card >= 6"></div>

    </div>

  </section>
  
</template>

<script>

export default {
  data() {
    return {
      count_card: 3
    }
  },
}

</script>

<style>

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Roboto', sans-serif;
}

section {
  height: 100vh;
  background-color: #d1caa1;
}

.top {
  padding-top: 3rem;
}

h1 {
  font-size: 3rem;
  color: #28213a;
  text-align: center;
}

.game-setup {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 10rem;
  margin-top: 2rem;
}

.full-counter {
  display: flex;
  align-items: center;
  justify-content: center;
}

.btn {
  height: 2rem;
  width: 2rem;
  background-color: white;
  border-radius: 0.5rem;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0.5rem;
  box-shadow: 2px 2px 20px 2px rgba(0,0,0,0.2);
  cursor: pointer;
}

.btn p {
  font-size: 1.5rem;
  color: #28213a;
}

.counter {
  height: 3rem;
  width: 3rem;
  background-color: white;
  border-radius: 0.75rem;
  display: flex;
  align-items: center;
  justify-content: center;
  border: solid #383b53 2px;
}

.counter p {
  font-size: 2rem;
  color: #28213a;
}

.green {
  background-color: rgb(38, 139, 38);
}

.red {
  background-color: rgb(164, 21, 21);
}

.red p {
  font-size: 0.75rem;
}

.start {
  height: 2.5rem;
  width: 6rem;
  border-radius: 0.625rem;
  background-color: #66717e;
  box-shadow: 2px 2px 20px 2px rgba(0,0,0,0.2);
  display: flex;
  align-items: center;
  justify-content: center;
  border: solid #383b53 2px;
  cursor: pointer;
}

.btn-start {
  color: #28213a;
  font-weight: bold;
}

.all-card {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  align-items: center;
  margin-top: 2rem;
}

.card {
  width: 55rem;
  height: 3rem;
  border-radius: 1rem;
  margin-top: 0.5rem;
}

.first {
  background-color: rgb(55, 110, 48);
}

.second {
  background-color: rgb(81, 112, 34);
}

.third {
  background-color: rgb(143, 137, 48);
}

.fourth {
  background-color: rgb(155, 110, 48);
}

.fifth {
  background-color: rgb(195, 97, 48);
}

.sixth {
  background-color: rgb(235, 48, 48);
}

</style>
