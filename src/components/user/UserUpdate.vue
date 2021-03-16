<template>
  <h2>User update : {{ data }}</h2>
  <button @click="back">Back</button>
</template>

<script>
import { useRoute } from "vue-router";
import { router } from "../../router";

export default {
  data() {
    return {
      data: "",
    };
  },
  mounted() {
    this.data = useRoute().params.name;
  },
  methods: {
    back() {
      router.back();
    },
  },
};
</script>