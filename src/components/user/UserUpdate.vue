<template>
  <h2>User update : {{ data }}</h2>
  <input type="text" v-model="userUpdate" />
  <button @click="back">Back</button>
</template>

<script>
import { useRoute } from "vue-router";
import { router } from "../../router";

export default {
  data() {
    return {
      userUpdate: "",
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
  watch: {
    userUpdate(newData, oldData) {
      console.log("new :", newData, " - old :", oldData);
    },
  },
};
</script>