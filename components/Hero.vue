<template>
  <section class="Hero">
    <div class="Hero_Inner">
      <div class="Hero_Data">
        <p
          v-if="data.shoulderCopy"
          class="Hero_Tagline"
          v-html="data.shoulderCopy"
        ></p>
        <h2
          v-if="data.titleCopy"
          class="Hero_Title"
          v-html="data.titleCopy"
        ></h2>
        <p v-if="data.text" class="Hero_Text" v-html="data.text"></p>
        <a
          v-if="data.ctaButton && data.ctaButton.label"
          class="Hero_Button"
          :href="data.ctaButton.url"
          rel="noreferrer noopener"
          :target="data.ctaButton.newTab ? '_blank' : ''"
          >{{ data.ctaButton.label }}</a
        >
      </div>
      <div v-if="data.backgroundImage" class="Hero_Image">
        <img :src="data.backgroundImage.src" width="540" height="370" alt="" />
      </div>
    </div>
  </section>
</template>

<script>
export default {
  props: {
    data: {
      type: Object,
      default() {
        return {
          shoulderCopy: '',
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
.Hero {
  margin: 0 0 60px 0;
  padding: 40px 0 0 0;
  background: #f8f8f8;
  text-align: center;
}
.Hero_Inner {
  min-width: 0;
  margin: 0 auto;
  padding: 0;
  position: relative;
}
.Hero_Tagline {
  color: #888;
  margin: 0 0 2px 0;
  padding: 0;
  font-size: 1.4rem;
}
.Hero_Title {
  margin: 0 0 20px 0;
  padding: 0;
  font-size: 2.4rem;
  line-height: 1.5;
  font-weight: bold;
}
.Hero_Text {
  margin: 0 0 16px 0;
  padding: 0;
  font-size: 1.4rem;
}
.Hero_Button {
  background: #fff;
  color: #1a73e8;
  border-radius: 4px;
  padding: 10px 20px;
  display: inline-block;
  text-decoration: none;
  font-weight: bold;
  transition: box-shadow 0.2s;
}
.Hero_Button:hover {
  box-shadow: 0 0 0 2px #005fcc;
}
.Hero_Image > img {
  width: 100%;
  height: auto;
  display: block;
}
.Hero_Image {
  width: 96%;
  max-width: 600px;
  margin: 0 auto;
}
@media (min-width: 600px) {
  .Hero {
    margin: 0 0 100px 0;
  }
  .Hero_Data {
    paddin: 0;
  }
  .Hero_Tagline {
    font-size: 1.6rem;
  }
  .Hero_Title {
    font-size: 2.8rem;
  }
  .Hero_Text {
    font-size: 1.6rem;
  }
  .Hero_Image {
    margin: 0 auto;
  }
}
@media (min-width: 960px) {
  .Hero {
    text-align: left;
    padding: 0 40px;
  }
  .Hero_Inner {
    display: flex;
    align-items: center;
    max-width: 1024px;
  }
  .Hero_Data {
    width: 40%;
    margin: 0 auto 0 28px;
  }
  .Hero_Image {
    width: 56%;
  }
}
</style>
