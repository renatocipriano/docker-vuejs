<template>
  <div class="item">
    <h2>{{ meme.name }}</h2>
    <img :src="meme.url" :alt="meme.name" :title="meme.name" />
  </div>
</template>

<script>
export default {
  name: "MemeBox",
  props: {
    meme: {
      required: true,
    },
  },
};
</script>
