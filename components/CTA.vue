<template>
  <section class="Cta">
    <h3 v-if="data.titleCopy" class="Cta_Title" v-html="data.titleCopy"></h3>
    <p v-if="data.text" class="Cta_Text" v-html="data.text"></p>
    <a
      v-if="data.ctaButton && data.ctaButton.label"
      class="Cta_Button"
      :href="data.ctaButton.url"
      rel="noreferrer noopener"
      :target="data.ctaButton.newTab ? '_blank' : ''"
      >{{ data.ctaButton.label }}</a
    >
  </section>
</template>

<script>
export default {
  props: {
    data: {
      type: Object,
      default() {
        return {
          titleCopy: '',
          text: '',
          ctaButton: {
            label: '',
            url: '',
            newTab: false,
          },
        }
      },
    },
  },
}
</script>

<style scoped>
.Cta {
  margin: 0 0 60px 0;
  padding: 40px 24px;
  background: #f8f8f8;
  text-align: center;
}
.Cta_Title {
  margin: 0 0 8px 0;
  padding: 0;
  font-size: 2rem;
  line-height: 1.5;
  font-weight: bold;
}
.Cta_Text {
  margin: 0 0 16px 0;
  padding: 0;
  font-size: 1.4rem;
  color: #888;
}
.Cta_Button {
  background: #fff;
  color: #1a73e8;
  border-radius: 4px;
  padding: 10px 20px;
  display: inline-block;
  text-decoration: none;
  font-weight: bold;
  transition: box-shadow 0.2s;
}
.Cta_Button:hover {
  box-shadow: 0 0 0 2px #005fcc;
}
@media (min-width: 600px) {
  .Cta {
    margin: 0 0 100px 0;
    padding: 60px 40px;
  }
  .Cta_Title {
    font-size: 2.4rem;
    margin: 0 0 16px 0;
  }
  .Cta_Text {
    font-size: 1.6rem;
    margin: 0 0 28px 0;
  }
}
</style>
