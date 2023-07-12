<template>
  <h1>Memes</h1>
  <section><MemeBox v-for="meme in memes" :key="meme.id" :meme="meme" /></section>
</template>

<script>
import axios from "axios";
import MemeBox from "@/components/MemeBox.vue";
export default {
  name: "HomePage",
  components: {
    MemeBox,
  },
  data() {
    return {
      memes: [],
    };
  },
  mounted() {
    axios
      .get(process.env.VUE_APP_API_URL)
      .then(({ data: { data } }) => (this.memes = data.memes));
  },
};
</script>
