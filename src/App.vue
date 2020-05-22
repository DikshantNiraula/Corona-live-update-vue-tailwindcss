<template>
  <div id="app" class="antialiased text-gray-100">
    <Navbar class="mb-4" />
    <div class="mx-8 mb-4">
      <div class="sm:flex items-center justify-center">
        <StatusBox
          class="bg-blue-700 my-4 hover:bg-blue-800"
          :info="info.tested_total"
          name="Total Tested"
        />
        <StatusBox
          class="bg-red-700 my-4 hover:bg-red-800"
          :info="info.tested_positive"
          name="Tested Positive"
        />
      </div>

      <div class="sm:flex items-center justify-center">
        <StatusBox
          class="bg-red-700 my-4 hover:bg-red-800"
          :info="info.deaths"
          name="Deaths"
        />
        <StatusBox
          class="bg-orange-600 my-4  hover:bg-orange-700"
          :info="info.recovered"
          name="Recovered"
        />
      </div>

      <div class="sm:flex items-center justify-center">
        <StatusBox
          class="bg-green-700 my-4 hover:bg-green-800"
          :info="info.tested_negative"
          name="Tested Negative"
        />
        <StatusBox
          class="bg-yellow-700 my-4 hover:bg-yellow-800"
          :info="info.quarantined"
          name="Quarantined"
        />
      </div>
    </div>

    <div
      class="w-full py-2 text-lg bg-blue-800 flex items-center justify-center text-center px-4"
    >
      <h1 class="text-white">
        ©️ copyright 2020 | Designed and Developed by
        <a
          href="https://www.facebook.com/dikshantKniraula"
          target="_blank"
          class="text-white "
        >
          Dikshant Niraula</a
        >
      </h1>
    </div>
  </div>
</template>

<script>
import Navbar from "./components/Navbar.vue";
import StatusBox from "./components/StatusBox.vue";
import axios from "axios";

export default {
  name: "App",
  components: {
    Navbar,
    StatusBox,
  },
  data() {
    return {
      info: null,
      name: null,
    };
  },

  mounted() {
    var myHeaders = new Headers();
    myHeaders.append("Content-Type", "application/json");

    var requestOptions = {
      method: "GET",
      headers: myHeaders,
      redirect: "follow",
    };

    axios
      .get("https://nepalcorona.info/api/v1/data/nepal", requestOptions)
      .then((response) => (this.info = response.data));
  },
};
</script>

<style src="../public/style.css"></style>
