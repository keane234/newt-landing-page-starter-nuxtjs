<template>
  <section class="Feature1">
    <h3
      v-if="data.titleCopy"
      class="Feature1_Title"
      v-html="data.titleCopy"
    ></h3>
    <p v-if="data.text" class="Feature1_Text" v-html="data.text"></p>
    <img
      v-if="data.image && data.image.src"
      :src="data.image.src"
      width="980"
      height="307"
      alt=""
      class="Feature1_Image"
    />
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
          image: null,
        }
      },
    },
  },
}
</script>

<style scoped>
.Feature1 {
  margin: 0 auto 60px auto;
  padding: 0 24px;
  text-align: center;
  max-width: 1024px;
}
.Feature1_Title {
  margin: 0 0 8px 0;
  padding: 0;
  font-size: 1.8rem;
  line-height: 1.5;
  font-weight: bold;
}
.Feature1_Text {
  margin: 0 0 20px 0;
  padding: 0;
  font-size: 1.4rem;
  color: #888;
}
.Feature1_Image {
  width: 100%;
  height: auto;
  display: block;
}
@media (min-width: 600px) {
  .Feature1 {
    margin: 0 auto 100px auto;
    padding: 0 40px;
  }
  .Feature1_Title {
    font-size: 2.4rem;
  }
  .Feature1_Text {
    margin: 0 0 36px 0;
    font-size: 1.6rem;
  }
}
</style>
