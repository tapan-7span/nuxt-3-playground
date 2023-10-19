<template>
  <div class="text-red-400 text-2xl">Nuxt Testing App</div>
  <div>
    <button class="bg-gray-400 border-gray-700 rounded p-2" @click="fetchData">
      Fetch Data
    </button>
  </div>
  <div>
    Response :
    {{ responseData }}
  </div>
</template>
<script>
export default {
  data() {
    return { responseData: null };
  },
  created() {},
  methods: {
    async fetchData() {
      const data = await this.$axios.$get("http://localhost:8008/items/blog");
      
      this.responseData = data?.data;
    },
  },
};
</script>
<style lang=""></style>
