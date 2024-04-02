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
            <button @click="openModal()" class="fas fa-question" id="button1"></button>
            <button @click="openInfo()" class="fas fa-info" id="button2"></button>
          </div>
        </div>
        <div class="modal" :class="{ 'is-active': demonstrateModal }">
          <div class="modal-background"></div>
          <div class="modal-dialog">
            <div class="modal-content">
              <div class="modal-header">
                <h5 class="modal-title">
                  Regras da sala de cinema
                </h5>
              </div>
              <div class="modal-body">
                <span>
                  <i class="fas fa-smoking-ban"></i>
                  Proibido fumar
                </span> <br>
                <span>
                  <i class="fas fa-mobile-alt"></i>
                  Proibido uso de celular
                </span> <br>
                <span>
                  <i class="fas fa-volume-up"></i>
                  Proibido qualquer tipo de som alto
                </span> <br>
                <span>
                  <i class="fas fa-video"></i>
                  Proibido a gravação do filme
                </span>
              </div>
              <div class="modal-footer">
                <button type="button" class="btn btn-secondary" @click="sealModal()">
                  Fechar
                </button>
              </div>
            </div>
          </div>
        </div>
        <div class="modal" :class="{ 'is-active': showModal }">
          <div class="modal-background"></div>
          <div class="modal-dialog">
            <div class="modal-content">
              <div class="modal-header">
                <h5 class="modal-title">
                  a
                </h5>
              </div>
              <div class="modal-body">
                <p>
                  Depois de se reunir com Gwen Stacy, Homem-Aranha é jogado no multiverso. Lá, o super-herói aracnídeo
                  encontra uma numerosa equipe encarregada de proteger sua própria existência.
                </p>
              </div>
              <div class="modal-footer">
                <button type="button" class="btn btn-secondary" @click="closeModal()">
                  Fechar
                </button>
              </div>
            </div>
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
            <button @click="startModal()" class="fas fa-question" id="button1"></button>
            <button @click="startInfo()" class="fas fa-info" id="button2"></button>
          </div>
          <div class="modal" :class="{ 'is-active': depictModal }">
            <div class="modal-background"></div>
            <div class="modal-dialog">
              <div class="modal-content">
                <div class="modal-header">
                  <h5 class="modal-title">
                    Regras da sala de cinema
                  </h5>
                </div>
                <div class="modal-body">
                  <span>
                    <i class="fas fa-smoking-ban"></i>
                    Proibido fumar
                  </span> <br>
                  <span>
                    <i class="fas fa-mobile-alt"></i>
                    Proibido uso de celular
                  </span> <br>
                  <span>
                    <i class="fas fa-volume-up"></i>
                    Proibido qualquer tipo de som alto
                  </span> <br>
                  <span>
                    <i class="fas fa-video"></i>
                    Proibido a gravação do filme
                  </span>
                </div>
                <div class="modal-footer">
                  <button type="button" class="btn btn-secondary" @click="shutModal()">
                    Fechar
                  </button>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="modal" :class="{ 'is-active': exposeModal }">
          <div class="modal-background"></div>
          <div class="modal-dialog">
            <div class="modal-content">
              <div class="modal-header">
                <h5 class="modal-title">
                  Deseja excluir essa anotação?
                </h5>
              </div>
              <div class="modal-body">
                <p>
                  Após formar uma família, Jake Sully e Ney'tiri fazem de tudo para ficarem juntos. No entanto, eles
                  devem sair de casa e explorar as regiões de Pandora quando uma antiga ameaça ressurge, e Jake deve
                  travar uma guerra difícil contra os humanos.
                </p>
              </div>
              <div class="modal-footer">
                <button type="button" class="btn btn-secondary" @click="endModal()">
                  Fechar
                </button>
              </div>
            </div>
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
            <button @click="joinModal()" class="fas fa-question" id="button1"></button>
            <button @click="joinInfo()" class="fas fa-info" id="button2"></button>
          </div>
          <div class="modal" :class="{ 'is-active': illustrateModal }">
            <div class="modal-background"></div>
            <div class="modal-dialog">
              <div class="modal-content">
                <div class="modal-header">
                  <h5 class="modal-title">
                    Regras da sala de cinema
                  </h5>
                </div>
                <div class="modal-body">
                  <span>
                    <i class="fas fa-smoking-ban"></i>
                    Proibido fumar
                  </span> <br>
                  <span>
                    <i class="fas fa-mobile-alt"></i>
                    Proibido uso de celular
                  </span> <br>
                  <span>
                    <i class="fas fa-volume-up"></i>
                    Proibido qualquer tipo de som alto
                  </span> <br>
                  <span>
                    <i class="fas fa-video"></i>
                    Proibido a gravação do filme
                  </span>
                </div>
                <div class="modal-footer">
                  <button type="button" class="btn btn-secondary" @click="blockedModal()">
                    Fechar
                  </button>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="modal" :class="{ 'is-active': displayModal }">
        <div class="modal-background"></div>
        <div class="modal-dialog">
          <div class="modal-content">
            <div class="modal-header">
              <h5 class="modal-title">
                Deseja excluir essa anotação?
              </h5>
            </div>
            <div class="modal-body">
              <p class="modal-text">
                Um homem deprimido que sofre de insônia conhece um estranho vendedor chamado Tyler Durden e se vê
                morando em uma casa suja depois que seu perfeito apartamento é destruído. A dupla forma um clube com
                regras rígidas onde homens lutam. A parceria perfeita é comprometida quando uma mulher, Marla, atrai a
                atenção de Tyler.
              </p>
            </div>
            <div class="modal-footer">
              <button type="button" class="btn btn-secondary" @click="finishModal()">
                Fechar
              </button>
            </div>
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
      cardStatus: ['Disponível', 'Disponível', 'Disponível'],
      showModal: false,
      exposeModal: false,
      displayModal: false,
      demonstrateModal: false,
      depictModal: false,
      illustrateModal: false
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
    },

    openModal() {
      this.showModal = true;
    },

    startModal() {
      this.exposeModal = true;
    },

    joinModal() {
      this.displayModal = true;
    },

    closeModal() {
      this.showModal = false;
    },

    endModal() {
      this.exposeModal = false;
    },

    finishModal() {
      this.displayModal = false;
    },

    openInfo() {
      this.demonstrateModal = true;
    },

    startInfo() {
      this.depictModal = true;
    },

    joinInfo() {
      this.illustrateModal = true;
    },

    sealModal() {
      this.demonstrateModal = false;
    },

    shutModal() {
      this.depictModal = false;
    },

    blockedModal() {
      this.illustrateModal = false;
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
  background-color: #ffffff;
  border: none;
  padding: 10px;
  cursor: pointer;
  transition: background-color 0.2s ease-in-out;
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

#button1 {
  background-color: #ffffff;
  position: absolute;
  bottom: 10px;
  right: 10px;
  justify-content: center;
  border-radius: 100%;
  margin: 0;
}

#button2 {
  background-color: #ffffff;
  position: absolute;
  bottom: 10px;
  right: 50px;
  justify-content: center;
  border-radius: 100%;
  margin: 0;
}

.fas-question {
  text-align: center;
  position: relative;

}

.fas-info {
  text-align: center;
  position: relative;
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

.modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  align-items: center;
  text-align: center;
  justify-content: center;
  display: none;
  margin: auto;
}

.modal-dialog {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
}

.modal-text {
  height: 155px;
  border-radius: 10px;
}

.modal-body {
  text-align: left;
}

.modal-content {
  width: 100%;
  height: 100%;
  border-radius: 9px;
  display: flex;
  margin: auto;
}

.btn-secondary {
  border-radius: 50px;
}

.modal.is-active {
  width: 100%;
  background: rgba(0, 0, 0, 0.79);
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
