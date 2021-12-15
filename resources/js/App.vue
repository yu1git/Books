<template>
  <div>
    {{ data.message }}
    <HelloWorld />
  </div>
</template>

<script>
import { reactive } from "vue";
import HelloWorld from "./components/HelloWorld";

import axios from "axios";

export default {
  name: "App",
  components: {
    HelloWorld,
  },
  setup() {
    const data = reactive({
      message: "Hello Vue!!!!!!!!",
    });
    const url = "サーバーのURL/api/books";
    const getAPI = async () => {
      const result = await axios.get(url);
      console.log(result);
    };

    getAPI();

    return {
      data,
      getAPI,
    };
  },
};
</script>