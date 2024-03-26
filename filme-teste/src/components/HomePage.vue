<template>
  <div class="carousel-container">
    <button class="prev-arrow" @click="prevCard">
      <i class="fas fa-chevron-left"></i>
    </button>

    <div class="carousel">
      <div class="card-1" v-show="currentCard === 0">
        <div class="card-content" :class="{ 'red-bg': cardStatus[0] === 'Indisponível' }">
          <h1>
            {{ cardStatus[0] }}
          </h1>
          <div class="image">
            <img src="../assets/aranha1.jpg" />
          </div>
          <div class="sub">
            <h2>
              Horários de exibição
            </h2>
            <p>
            <ul>
              <li>13:00/Sala 2</li>
              <li>18:30/Sala 1</li>
              <li>20:00/Sala 6</li>
            </ul>
            </p>
          </div>
        </div>
      </div>

      <div class="card-2" v-show="currentCard === 1">
        <div class="card-content" :class="{ 'red-bg': cardStatus[1] === 'Indisponível' }">
          <h1>
            {{ cardStatus[1] }}
          </h1>
          <div class="image">
            <img src="../assets/avatar.jpg" />
          </div>
          <div class="sub">
            <h2>
              Horários de exibição
            </h2>
            <p>
            <ul>
              <li>13:00/Sala 2</li>
              <li>18:30/Sala 1</li>
              <li>20:00/Sala 6</li>
            </ul>
            </p>
          </div>
        </div>
      </div>

      <div class="card-3" v-show="currentCard === 2">
        <div class="card-content" :class="{ 'red-bg': cardStatus[2] === 'Indisponível' }">
          <h1>
            {{ cardStatus[2] }}
          </h1>
          <div class="image">
            <img src="../assets/clube.jpg" />
          </div>
          <div class="sub">
            <h2>
              Horários de exibição
            </h2>
            <p>
            <ul>
              <li>13:00/Sala 2</li>
              <li>18:30/Sala 1</li>
              <li>20:00/Sala 6</li>
            </ul>
            </p>
          </div>
        </div>
      </div>
    </div>

    <button class="next-arrow" @click="nextCard">
      <i class="fas fa-chevron-right"></i>
    </button>
  </div>
</template>

<script>
export default {
  name: 'HomePage',
  data() {
    return {
      currentCard: 0,
      cardStatus: ['Disponível', 'Disponível', 'Disponível']
    };
  },
  created() {
    setInterval(this.updateCardStatus, 60 * 1000);
  },

  methods: {
    prevCard() {
      if (this.currentCard > 0) {
        this.currentCard--;
      }
    },

    nextCard() {
      if (this.currentCard < 2) {
        this.currentCard++;
      }
    },

    updateCardStatus() {
      for (let i = 0; i < this.cardStatus.length; i++) {
        if (this.cardStatus[i] === 'Disponível') {
          this.cardStatus[i] = 'Indisponível';
        } else {
          this.cardStatus[i] = 'Disponível';
        }
      }
    }
  },
};
</script>

<style scoped>
.carousel-container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin: 0 auto;
  width: 80%;
}

.prev-arrow,
.next-arrow {
  background-color: #ccc;
  padding: 10px;
  border-radius: 50%;
  cursor: pointer;
  transition: background-color 0.2s ease-in-out;
}

.prev-arrow:hover,
.next-arrow:hover {
  background-color: #aaa;
}

.carousel {
  display: flex;
  transition: transform 0.5s ease-in-out;
}

.card-content {
  position: relative;
  overflow-y: hidden;
  overflow-x: hidden;
  height: 650px;
  width: 340px;
  margin: 0 10px auto;
  padding: 20px;
  background-color: #00ff00;
  border-radius: 10px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  display: flex;
  justify-content: center
}

.red-bg {
  background-color: #ff0000;
}

h1 {
  position: absolute;
  top: 1px;
  left: 0;
  width: 100%;
  text-align: center;
}

h2 {
  position: absolute;
  z-index: 1;
  bottom: 60px;
  left: 0;
  background-color: #ffffff;
  text-align: center;
  width: 100%;
  height: 40px;
}

p {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 80px;
  padding: 10px;
  margin: 0;
  background-color: #ffffff;
}

.card-1,
.card-2,
.card-3 {
  display: none;
}

.card-1,
.card-2,
.card-3 {
  display: block;
}

img {
  margin: auto;
  align-items: center;
}

.image {
  align-items: center;
  margin: auto;
  justify-content: center;
  margin-top: 25px;
  position: relative;
}
</style>
