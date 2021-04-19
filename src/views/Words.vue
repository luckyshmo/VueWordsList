<template>
  <div class="home">
    <v-item-group>
    <v-container>
      <v-row>
        <v-col
          v-for="n in 64"
          :key="n"
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
                <div>Word of the Day</div>
                <p class="display-1 text--primary">
                  el·ee·mos·y·nar·y
                </p>
                <p>adjective</p>
                <div class="text--primary">
                  relating to or dependent on charity; charitable.<br>
                  "an eleemosynary educational institution."
                </div>
              </v-card-text>
              <v-card-actions>
                <v-btn
                  text
                  color="teal accent-4"
                  @click="reveal = true"
                >
                  Learn More
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
                      Origin
                    </p>
                    <p>late 16th century (as a noun denoting a place where alms were distributed): from medieval Latin eleemosynarius, from late Latin eleemosyna ‘alms’, from Greek eleēmosunē ‘compassion’ </p>
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
// @ is an alias to /src
// import Words from '@/components/Words.vue'

export default {
  name: 'Words',
  components: {
    // Words
  }
}
</script>

<script>
  export default {
    data: () => ({
      reveal: false,
    }),
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
