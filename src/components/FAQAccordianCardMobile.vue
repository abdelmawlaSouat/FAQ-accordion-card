<template>
  <div id="accordian-card-mobile">
    <v-card
      class="custom-card rounded-card"
    >
      <!-- Illustrations -->
      <img
        class="woman-img"
        :src="require('@/assets/illustration-woman-online-mobile.svg')"
        alt="Illustration Woman"
      />

      <!-- FAQ -->
      <div class="content-text">
        <h2>FAQ</h2>
        <v-expansion-panels flat>
          <v-expansion-panel v-for="(item, i) in items" :key="i">
            <v-expansion-panel-header @click="rotateArrow(item)">
                  {{ item.question }}
                 <template v-slot:actions>
                   <v-img
                    :class="item.class"
                    :src="require('@/assets/icon-arrow-down.svg')"
                    alt="Arrow"
                  ></v-img>
                  </template>
            </v-expansion-panel-header>
            <v-expansion-panel-content> {{ item.answer }} </v-expansion-panel-content>
          </v-expansion-panel>
        </v-expansion-panels>
      </div>

    </v-card>
  </div>
</template>

<script>
export default {
  name: 'FAQAccordianCardDesktop',
  props: {
    items: Object
  },
  methods: {
    rotateArrow (item) {
      item.class = (item.class === 'arrow-down') ? 'arrow-up' : 'arrow-down'
    }
  }
}
</script>

<style>
#accordian-card-mobile {
  padding: 2rem;
}
#accordian-card-mobile .custom-card {
  margin-top: 15vh;
  display: flex;
  flex-direction: column;
  align-items: center;
}
#accordian-card-mobile h2 {
  text-align: center;
}
#accordian-card-mobile .content-text {
  padding: 7rem 1rem 2rem 0;
}
#accordian-card-mobile .woman-img {
  position: absolute;
  top: -15vh;
}
.rounded-card {
  border-radius: 20px !important;
}
.py-4 {
  padding-top: 4rem;
  padding-bottom: 4rem;
}
.v-expansion-panel-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.v-expansion-panel-header--active {
  font-weight: 700 !important;
  color: hsl(237, 12%, 33%) !important;
}
.v-expansion-panel-header:hover {
  color: hsl(14, 88%, 65%);
}
.v-expansion-panel-content {
  color: hsl(240, 6%, 50%);
  font-size: 12px;
}
.arrow-up {
  transform: rotate(180deg);
}
</style>
