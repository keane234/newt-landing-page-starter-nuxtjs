<template>
  <section class="Logos">
    <h3 v-if="data.text" class="Logos_Title" v-html="data.text"></h3>
    <ul class="Logos_List">
      <li v-for="logo in data.logoImages" :key="logo._id">
        <img :src="logo.src" width="125" height="46" alt="" />
      </li>
    </ul>
  </section>
</template>

<script>
export default {
  props: {
    data: {
      type: Object,
      default() {
        return {
          text: '',
          logoImages: [],
        }
      },
    },
  },
}
</script>

<style scoped>
.Logos {
  margin: 0 0 60px 0;
  padding: 0 24px;
}
.Logos_Title {
  text-align: center;
  color: #888;
  font-weight: normal;
  font-size: 1.6rem;
  margin: 0 0 16px 0;
  padding: 0;
}
.Logos_List {
  margin: 0;
  padding: 0;
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
}
.Logos_List > li {
  margin: 4px;
  padding: 0;
  list-style: none;
  width: 100px;
  height: 36px;
}
.Logos_List > li > img {
  display: block;
  width: 100%;
  height: 100%;
  object-fit: contain;
}
@media (min-width: 600px) {
  .Logos {
    padding: 0 40px;
    margin: 0 0 100px 0;
  }
  .Logos_List > li {
    margin: 8px;
    width: 125px;
    height: 46px;
  }
}
</style>
