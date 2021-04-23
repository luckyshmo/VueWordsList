<template>
  <div class="home">
    <v-item-group>
    <v-container>
      <v-row>
        <v-col
          v-for="card in cards"
          :key="card.id"
          cols=auto
          md="3"
        >
          <v-item v-slot="{}">
            <v-card
              class="mx-auto"
              @click="cardClick(card.id)"
            >
              <v-card-text>
                <p class="display-1 text--primary">
                  {{card.title}}
                </p>
                <p>{{card.type}}</p>
                <div class="text--primary">
                  {{card.description}}
                </div>
              </v-card-text>
              <v-card-actions>
                <v-btn 
                  icon
                  v-on:click.stop
                  @click="editCard(card.id)"
                >
                  <v-icon color="primary lighten-2">mdi-pencil</v-icon>
                </v-btn>
                <v-btn 
                  icon
                  v-on:click.stop
                  @click="deleteCard(card.id)"
                >
                  <v-icon color="primary lighten-2">mdi-delete</v-icon>
                </v-btn>
              </v-card-actions>

              <v-expand-transition>
                <v-card
                  v-if="card.reveal"
                  class="transition-fast-in-fast-out v-card--reveal"
                  style="height: 100%; position: absolute"
                >
                  <v-card-text class="pb-0">
                    <p class="display-1 text--primary">
                      {{card.translation}}
                    </p>
                    <p> Русское описание, синонимы? <br>
                     ну чего нить найду... </p>
                  </v-card-text>
                  <v-card-actions class="pt-0">
                    <p>Some actions?</p>
                  </v-card-actions>
                </v-card>
              </v-expand-transition>

            </v-card>
          </v-item>
        </v-col>
      </v-row>
    </v-container>
  </v-item-group>
  </div>
</template>

<script>
  export default {
    name: 'Cards',
    data() { 
      return {
        cards: [
          {
            id: 1,
            title: 'Kek',
            type: 'Tech',
            translation: 'Лол',
            description: 'Суперсмешной такой вообще совсем очень кекнутный лол',
            reveal: false,
          },
          {
            id: 2,
            title: 'Mek',
            type: 'Common',
            translation: 'Лол',
            description: '',
            reveal: false,
          },
          {
            id: 3,
            title: 'Lol',
            type: 'Rare',
            translation: 'Лол',
            description: '',
            reveal: false,
          },
          {
            id: 4,
            title: 'Kek',
            type: 'Tech',
            translation: 'Лол',
            description: '',
            reveal: false,
          },
          {
            id: 5,
            title: 'Mek',
            type: 'Common',
            translation: 'Лол',
            description: '',
            reveal: false,
          },
          {
            id: 6,
            title: 'Loh',
            type: 'Rare',
            translation: 'Лох',
            description: 'Типичный чувачок с района',
            reveal: false,
          },
          {
            id: 7,
            title: 'Keki',
            type: 'Tech',
            translation: 'Кеки',
            description: 'Many keks',
            reveal: false,
          },
          {
            id: 8,
            title: 'Meki',
            type: 'Common',
            translation: 'Меки',
            description: '?????',
            reveal: false,
          },
          {
            id: 9,
            title: 'Loli',
            type: 'Rare',
            translation: 'Лоли',
            description: 'Не трожь!',
            reveal: false,
          },
        ],
      }
    },
    methods: {

      cardClick(id) {
        console.log('id ', id)
        let card = this.cards.filter(card => card.id === id)[0]
        card.reveal = !card.reveal
      },

      editCard(id) {
        console.log('id edit', id)
      },

      deleteCard(id) {
        this.cards = this.cards.filter(card => card.id !== id)
        console.log('id deleted', id)
      }
    },

  }
</script>

<style scope>
.v-card--reveal {
  bottom: 0;
  opacity: 1 !important;
  position: absolute;
  width: 100%;
}
</style>
