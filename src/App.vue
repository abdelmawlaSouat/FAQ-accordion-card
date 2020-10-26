<template>
  <div id="app">
    <FAQAccordianCardMobile
      v-if="this.$vuetify.breakpoint.xsOnly"
      :items="items"
    />
    <FAQAccordianCardDesktop
      v-else
      :items="items"
    />
  </div>
</template>

<script>
import FAQAccordianCardDesktop from './components/FAQAccordianCardDesktop.vue'
import FAQAccordianCardMobile from './components/FAQAccordianCardMobile.vue'

export default {
  name: 'App',
  components: {
    FAQAccordianCardDesktop,
    FAQAccordianCardMobile
  },
  data () {
    return {
      items: {
        item0: {
          question: 'How many team members can I invite?',
          answer: 'You can invite up to 2 additional users on the Free plan. There is no limit on team members for the Premium plan.',
          class: 'arrow-down'
        },
        item1: {
          question: 'What is the maximum file upload size?',
          answer: 'No more than 2GB. All files in your account must fit your allotted storage space.',
          class: 'arrow-down'
        },
        item2: {
          question: 'How do I reset my password?',
          answer: 'Click “Forgot password” from the login page or “Change password” from your profile page. A reset link will be emailed to you.',
          class: 'arrow-down'
        },
        item3: {
          question: 'Can I cancel my subscription?',
          answer: 'Yes! Send us a message and we’ll process your request no questions asked.',
          class: 'arrow-down'
        },
        item4: {
          question: 'Do you provide additional support?',
          answer: 'Chat and email support is available 24/7. Phone lines are open during normal business hours.',
          class: 'arrow-down'
        }
      }
    }
  }
}
</script>

<style>

@font-face {
  font-family: "Kumbh Sans";
  src: local("Kumbh Sans"),
  url(./fonts/KumbhSans-Regular.ttf) format("truetype");
}

#app {
  font-family: "Kumbh Sans", Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  height: 100vh;

}
body {
  background: linear-gradient(hsl(273, 75%, 66%), hsl(240, 73%, 65%));
}
</style>
