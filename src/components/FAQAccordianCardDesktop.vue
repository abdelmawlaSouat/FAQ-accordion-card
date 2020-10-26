<template>
  <div id="accordian-card-desktop">

    <v-card
      class="custom-card force-flex rounded-card"
      :width="900"
    >
      <!-- Illustrations -->
      <div class="imgs-container">
        <div class="woman-img-container">
          <img
            class="woman-img py-4"
            :src="require('@/assets/illustration-woman-online-desktop.svg')"
            alt="Illustration Woman"
            />
        </div>

        <img
          :src="require('@/assets/illustration-box-desktop.svg')"
          alt="Illustration Box"
          class="box-img"
        >
      </div>

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
#accordian-card-desktop {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
}
.force-flex {
  display: flex !important;
}
.rounded-card {
  border-radius: 20px !important;
}
#accordian-card-desktop h2 {
  padding: 16px 24px;
}
.py-4 {
  padding-top: 4rem;
  padding-bottom: 4rem;
}
#accordian-card-desktop .woman-img-container {
  width: 100%;
  overflow: hidden;
}
#accordian-card-desktop .content-text {
  padding: 3.5rem 3rem 2rem 0;
}
#accordian-card-desktop .woman-img {
  position: relative;
  left: -8vh;
}
#accordian-card-desktop .box-img {
  position: absolute;
  top: 21vh;
  left: -12vh;
  width: 200px;
  height: 200px;
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
.imgs-container {
  background: url('~@/assets/bg-pattern-desktop.svg');
}
.arrow-up {
  transform: rotate(180deg);
}
</style>
