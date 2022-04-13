<template>
  <section>
    <div class="top">
      <h1>Random Challenger Gameplay</h1>
    </div>

    <div class="game-setup">
      <div class="full-counter">
        <input class="btn green" type="button" value="-" @click="count_card--" v-if="count_card >= 3">
        <input class="btn red" type="button" value="Min" v-if="count_card == 2">

        <div class="counter">
          <p>{{ count_card }}</p>
        </div>

        <input class="btn green" type="button" value="+" @click="count_card++" v-if="count_card <= 5">
        <input class="btn red" type="button" value="Max" v-if="count_card == 6">
      </div>

      <input class="start" type="button" value="Roll" @click="roll">
    </div>

    <div class="all-card" v-if="list_of_challenge_restricted != '' " >

      <p class="card first">{{ challenge[first] }}</p>
      <p class="card second">{{ challenge[second] }}</p>
      <p class="card third" v-if="count_card >= 3">{{ challenge[third] }}</p>
      <p class="card fourth" v-if="count_card >= 4">{{ challenge[fourth] }}</p>
      <p class="card fifth" v-if="count_card >= 5">{{ challenge[fifth] }}</p>
      <p class="card sixth" v-if="count_card >= 6">{{ challenge[sixth] }}</p>

    </div>

  </section>
  
</template>

<script>

export default {
  methods: {
    randomRoll : function(){
      return Math.floor(Math.random() * this.challenge.length)
    },

    roll : function(){
      this.list_of_challenge_restricted = []

      this.first = this.randomRoll()
      this.restrictionAdd(this.first)

      this.second = this.randomRoll()
      for (let i = 0; i < this.list_of_challenge_restricted.length; i++) {
        if (this.second == this.list_of_challenge_restricted[i]) {
          this.second = this.randomRoll()
          i = -1
        }
      }
      this.restrictionAdd(this.second)

      this.third = this.randomRoll()
      for (let i = 0; i < this.list_of_challenge_restricted.length; i++) {
        if (this.third == this.list_of_challenge_restricted[i]) {
          this.third = this.randomRoll()
          i = -1
        }
      }
      this.restrictionAdd(this.third)

      this.fourth = this.randomRoll()
      for (let i = 0; i < this.list_of_challenge_restricted.length; i++) {
        if (this.fourth == this.list_of_challenge_restricted[i]) {
          this.fourth = this.randomRoll()
          i = -1
        }
      }
      this.restrictionAdd(this.fourth)

      this.fifth = this.randomRoll()
      for (let i = 0; i < this.list_of_challenge_restricted.length; i++) {
        if (this.fifth == this.list_of_challenge_restricted[i]) {
          this.fifth = this.randomRoll()
          i = -1
        }
      }
      this.restrictionAdd(this.fifth)

      this.sixth = this.randomRoll()
      for (let i = 0; i < this.list_of_challenge_restricted.length; i++) {
        if (this.sixth == this.list_of_challenge_restricted[i]) {
          this.sixth = this.randomRoll()
          i = -1
        }
      }
      this.restrictionAdd(this.sixth)
    },

    restrictionAdd : function(number){
      if (number == 0) {
        this.list_of_challenge_restricted.push(0)
      }

      if (number == 1 || number == 2 ||  number == 3) {
        this.list_of_challenge_restricted.push(1)
        this.list_of_challenge_restricted.push(2)
        this.list_of_challenge_restricted.push(3)
      }

      if (number == 4) {
        this.list_of_challenge_restricted.push(4)
      }

      if (number == 5 || number == 6) {
        this.list_of_challenge_restricted.push(5)
        this.list_of_challenge_restricted.push(6)
      }

      if (number == 7) {
        this.list_of_challenge_restricted.push(7)
      }

      if (number == 8) {
        this.list_of_challenge_restricted.push(8)
      }

      if (number == 9 || number == 10 ||  number == 11) {
        this.list_of_challenge_restricted.push(9)
        this.list_of_challenge_restricted.push(10)
        this.list_of_challenge_restricted.push(11)
      }

      if (number == 12 || number == 13) {
        this.list_of_challenge_restricted.push(12)
        this.list_of_challenge_restricted.push(13)
      }

      if (number == 14 || number == 15) {
        this.list_of_challenge_restricted.push(14)
        this.list_of_challenge_restricted.push(15)
      }

      if (number == 16 || number == 17) {
        this.list_of_challenge_restricted.push(16)
        this.list_of_challenge_restricted.push(17)
      }

      if (number == 18 || number == 19 || number == 20 || number == 21 || number == 22) {
        this.list_of_challenge_restricted.push(18)
        this.list_of_challenge_restricted.push(19)
        this.list_of_challenge_restricted.push(20)
        this.list_of_challenge_restricted.push(21)
        this.list_of_challenge_restricted.push(22)
      }

      if (number == 23 || number == 24 || number == 25 || number == 26) {
        this.list_of_challenge_restricted.push(23)
        this.list_of_challenge_restricted.push(24)
        this.list_of_challenge_restricted.push(25)
        this.list_of_challenge_restricted.push(26)
      }

      if (number == 27 || number == 28 || number == 29) {
        this.list_of_challenge_restricted.push(27)
        this.list_of_challenge_restricted.push(28)
        this.list_of_challenge_restricted.push(29)
      }

      if (number == 30 || number == 31) {
        this.list_of_challenge_restricted.push(30)
        this.list_of_challenge_restricted.push(31)
      }

      if (number == 32) {
        this.list_of_challenge_restricted.push(32)
        this.list_of_challenge_restricted.push(33)
      }

      if (number == 33) {
        this.list_of_challenge_restricted.push(32)
        this.list_of_challenge_restricted.push(33)
        this.list_of_challenge_restricted.push(34)
        this.list_of_challenge_restricted.push(35)
        this.list_of_challenge_restricted.push(42)
      }

      if (number == 34) {
        this.list_of_challenge_restricted.push(33)
        this.list_of_challenge_restricted.push(34)
        this.list_of_challenge_restricted.push(35)
        this.list_of_challenge_restricted.push(41)
      }

      if (number == 35) {
        this.list_of_challenge_restricted.push(33)
        this.list_of_challenge_restricted.push(34)
        this.list_of_challenge_restricted.push(35)
        this.list_of_challenge_restricted.push(43)
      }

      if (number == 36 || number == 37 || number == 38 || number == 39 || number == 40) {
        this.list_of_challenge_restricted.push(36)
        this.list_of_challenge_restricted.push(37)
        this.list_of_challenge_restricted.push(38)
        this.list_of_challenge_restricted.push(39)
        this.list_of_challenge_restricted.push(40)
      }

      if (number == 41) {
        this.list_of_challenge_restricted.push(34)
        this.list_of_challenge_restricted.push(41)
        this.list_of_challenge_restricted.push(42)
        this.list_of_challenge_restricted.push(43)
      }

      if (number == 42) {
        this.list_of_challenge_restricted.push(33)
        this.list_of_challenge_restricted.push(41)
        this.list_of_challenge_restricted.push(42)
        this.list_of_challenge_restricted.push(43)
      }

      if (number == 43) {
        this.list_of_challenge_restricted.push(35)
        this.list_of_challenge_restricted.push(41)
        this.list_of_challenge_restricted.push(42)
        this.list_of_challenge_restricted.push(43)
      }

      if (number == 44) {
        this.list_of_challenge_restricted.push(44)
      }

      if (number == 45) {
        this.list_of_challenge_restricted.push(45)
      }

      if (number == 46) {
        this.list_of_challenge_restricted.push(46)
      }

      if (number == 47) {
        this.list_of_challenge_restricted.push(47)
      }

      if (number == 48 || number == 49 || number == 50 || number == 51 || number == 52 || number == 53 || number == 54 || number == 55 || number == 56 || number == 57) {
        this.list_of_challenge_restricted.push(48)
        this.list_of_challenge_restricted.push(49)
        this.list_of_challenge_restricted.push(50)
        this.list_of_challenge_restricted.push(51)
        this.list_of_challenge_restricted.push(52)
        this.list_of_challenge_restricted.push(53)
        this.list_of_challenge_restricted.push(54)
        this.list_of_challenge_restricted.push(55)
        this.list_of_challenge_restricted.push(56)
        this.list_of_challenge_restricted.push(57)
      }

      if (number == 58) {
        this.list_of_challenge_restricted.push(58)
      }
    }
  },
  data() {
    return {
      count_card: 4,

      first : 0,
      second : 0,
      third : 0,
      fourth : 0,
      fifth : 0,
      sixth : 0,

      list_of_challenge_restricted : [],

      challenge : [
        "Le back ? non non, tu rentre à pieds 😁", //1

        "A chaque mort, tu t'endete de 500 gold", //2
        "A chaque mort, tu t'endete de 1000 gold",
        "A chaque mort, tu t'endete de 1500 gold",

        "Tu veut acheter un items ? Tu devras le revendre avant", //3

        "Des morceaux d'items ça existe pas, seulement les complets", //4
        "C'est la crise, seul les composants d'items sont dans tes moyens",

        "Les objets mythiques, connais pas", //5

        "Chaque mort(s) tu zoomeras de 1 cran de molette", //6

        "Tu n'apprendras pas ton A", //7
        "Tu n'apprendras pas ton Z", 
        "Tu n'apprendras pas ton E", 

        "Tu n'apprendras pas ton R", //8
        "Tu es impulsif, ton R doit etre en permanence en cooldown si possible (tu doit obligatoirement l'apprendre)",

        "Tu n'as le droit de monter un sort que tout les 2 niveaux (Au niveau 1 tu n'as pas sort)", //9
        "Tu es con, tu peut monter tes sorts seulement quand tu a 2 points disponible (et tu devras les mettres dans le meme sort)(Tu peut prendre un sort au niveau 1 puis la règle s'applique)",
        
        "Le niveau de tes sorts sont restreints à 4", //10
        "Le niveau de tes sorts sont restreints à 3",

        "Pour les AD first items GA, et les AP ça sera un Zhonia", //11
        "Tu es triste, tu achete une larme (mais tu la garde, pas le droit de l'évoluer)",
        "Tu es seul, l'amour de ta vie ta quitté, ton coeur est gélé (Tu achete un coeur gelé en first item)",
        "Tu as péché mon enfant, tu es condamnée à l'anathème (Tu achète chaîne de l'anathème en first item)",
        "Tu es un sculpteur hors paire, tu te fabrique toi meme ton armure (tu achete un lithoplastron de gargouille en first item)",

        "Tu te transforme en africain, tu n'as pas le droit d'acheter de bottes", //12
        "Bottes de mobilité obligatoire pour tout le monde",
        "Bottes du berzerk obligatoire pour tout le monde",
        "Chaussures de sorcier obligatoire pour tout le monde",

        "A chaque fois que tu passe par la base, tu repart avec 5 potions et 2 pinks", //13
        "A chaque fois que tu passe par la base, tu repart avec 5 potions",
        "A chaque fois que tu passe par la base, tu repart avec 2 pinks",

        "La nature des champions s'inverse, les ADs deviennent des magiciens et les APs des barbares sanguins", //14
        "Tu cosplay ton personnage preféré dans l'équipe ennemie, tu build le même stuff",

        "La foret est trop effrayante, seul la rivière pourras te guidée", //15

        "La midlane est corrompue, elle est devenue innaccessible", //15 //16

        "Il y a eu un eboulement sur la toplane, elle est devenue innaccessible", //16
        "Une terrible malédiction s'est abbatue sur la botlane, elle est devenue innaccessible",

        "Un dieu apparait, il s'agit du 1er champion de l'ecran de chargment, il est immortel (interdit de le tué)", //17
        "Un dieu apparait, il s'agit du 2eme champion de l'ecran de chargment, il est immortel (interdit de le tué)",
        "Un dieu apparait, il s'agit du 3eme champion de l'ecran de chargment, il est immortel (interdit de le tué)",
        "Un dieu apparait, il s'agit du 4eme champion de l'ecran de chargment, il est immortel (interdit de le tué)",
        "Un dieu apparait, il s'agit du 5eme champion de l'ecran de chargment, il est immortel (interdit de le tué)",
        
        "Les tourelles du top sont invincibles (Interdictions de les taper)", //18
        "Les tourelles du mid sont invincibles (Interdictions de les taper)",
        "Les tourelles du bot sont invincibles (Interdictions de les taper)",

        "Ta barre espace est casser ! Caméra lock pour tout le monde", //19

        "Challenge 0 Cs, tout les 15 cs tu doit mourrir a tes risques et périls", //20 //18

        "Tu es une frousarde, les creeps t'emmenent sur ta voie", //21

        "Surexcité, tu utilise tes summoner spells dès que possible", //22

        "Combo n°1 : Smite et Téléportation", //23
        "Combo n°2 : Ghost et Purge",
        "Combo n°3 : Heal et Ignite",
        "Combo n°4 : Exhaust et Barrière",
        "Combo n°5 : Exhaust et Téléportation",
        "Combo n°6 : Flash et Barrière",
        "Combo n°7 : Smite et Ghost",
        "Combo n°8 : Heal et Purge",
        "Combo n°9 : Ignite et Ghost",
        "Combo n°10 : Flash et Rien (tu n'utilise pas le 2è summoner, sinon tu vend un item complet)",

        "Les duo laner ne doivent pas etre égoïste, ils doivent tout les deux participé a chaque éliminations, sinon le duo crash (imposibilité d'éffectué n'importe quelle actions pendant 15 secondes)", //24
        ],
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
  height: auto;
  min-height: 100vh;
  background-color: #d1caa1;
}

.top {
  padding-top: 3rem;
}

h1 {
  font-size: 3rem;
  line-height: 3.1rem;
  color: #28213a;
  text-align: center;
}

.game-setup {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 2rem;
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
  border: solid rgb(17, 58, 17) 2px;
}

.red {
  background-color: rgb(164, 21, 21);
  border: solid rgb(66, 7, 7) 2px;
  font-size: 0.75rem;
  color: white;
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
  color: #28213a;
  font-weight: bold;
  font-size: 1rem;
}

.all-card {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  align-items: center;
  margin-top: 2rem;
}

.card {
  width: 80%;
  min-height: 3rem;
  border-radius: 1rem;
  margin-top: 0.5rem;
  margin-bottom: 0.5rem;
  padding: 1rem;
  color: #28213a;
  font-size: 1.5rem;
}

.first {
  background-color: rgb(117, 173, 110);
}

.second {
  background-color: rgb(125, 150, 94);
}

.third {
  background-color: rgb(194, 187, 93);
}

.fourth {
  background-color: rgb(192, 144, 77);
}

.fifth {
  background-color: rgb(216, 119, 71);
}

.sixth {
  background-color: rgb(223, 68, 68);
}

</style>
