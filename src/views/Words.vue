<template>
  <div class="home">
    <v-item-group>
    <v-container>
      <v-row>
        <v-col
          v-for="word in words"
          :key="word.id"
          cols="22"
          md="4"
        >
          <v-item v-slot="{ active, toggle }">
            <v-card
              class="mx-auto"
              :color="active ? 'primary' : ''"
              @click="toggle"
            >
              <v-card-text>
                <p class="display-1 text--primary">
                  {{word.title}}
                </p>
                <p>{{word.type}}</p>
                <div class="text--primary">
                  {{word.description}}
                </div>
              </v-card-text>
              <v-card-actions>
                <v-btn
                  text
                  color="teal accent-4"
                  @click="reveal = true"
                >
                  Translation
                </v-btn>
              </v-card-actions>

              <v-expand-transition>
                <v-card
                  v-if="reveal"
                  class="transition-fast-in-fast-out v-card--reveal"
                  style="height: 100%;"
                >
                  <v-card-text class="pb-0">
                    <p class="display-1 text--primary">
                      {{word.translation}}
                    </p>
                    <p> Русское описание, синонимы? </br>
                     ну чего нить найду... </p>
                  </v-card-text>
                  <v-card-actions class="pt-0">
                    <v-btn
                      text
                      color="teal accent-4"
                      @click="reveal = false"
                    >
                      Close
                    </v-btn>
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
    data: () => ({ 
      drawer: null,
      words: [
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
    })
  }
</script>

<style>
.v-card--reveal {
  bottom: 0;
  opacity: 1 !important;
  position: absolute;
  width: 100%;
}
</style>
