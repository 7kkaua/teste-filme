<template>
  <div class="carousel-container">
    <button class="prev-arrow" @click="prevCard">
      <i class="fas fa-chevron-left"></i>
    </button>

    <div class="carousel">
      <div class="card" v-for="card in cards" :key="card.id" :class="{ active: card.isActive }">
        <h2>{{ card.title }}</h2>
        <p>{{ card.description }}</p>
      </div>
    </div>

    <button class="next-arrow" @click="nextCard">
      <i class="fas fa-chevron-right"></i>
    </button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      cards: [
        { id: 1, title: "Card 1", description: "Descrição do Card 1", isActive: true },
        { id: 2, title: "Card 2", description: "Descrição do Card 2", isActive: false },
        { id: 3, title: "Card 3", description: "Descrição do Card 3", isActive: false },
      ],
      currentCard: 0,
    };
  },
  methods: {
    prevCard() {
      if (this.currentCard > 0) {
        this.currentCard--;
        this.updateActiveCards();
      }
    },
    nextCard() {
      if (this.currentCard < this.cards.length - 1) {
        this.currentCard++;
        this.updateActiveCards();
      }
    },
    updateActiveCards() {
      for (const card of this.cards) {
        card.isActive = false;
      }
      this.cards[this.currentCard].isActive = true;
    },
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
  overflow-x: auto;
  transition: transform 0.5s ease-in-out;
}

.card {
  height: 600px;
  width: 400px;
  margin: 0 10px auto;
  padding: 20px;
  background-color: #fff;
  border-radius: 10px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  display: none;
}

.active {
  display: block;
}
</style>
