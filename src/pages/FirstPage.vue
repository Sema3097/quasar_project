<template>
  <div class="q-pa-md" style="max-width: 400px; margin: 0 auto">
    <q-form @submit.prevent class="q-gutter-md">
      <q-input v-model="dataToSend.name" label="Name" />
      <q-input v-model="dataToSend.surname" label="Surname" />
      <q-select v-model="dataToSend.city" :options="options" label="City" />
      <q-input v-model="dataToSend.email" label="Email" />
      <q-input v-model="dataToSend.date" filled type="date" hint="Date" />
      <div>
        <q-btn label="Save" type="submit" color="primary" @click="postData" />
      </div>
    </q-form>
  </div>
</template>

<script setup>
defineOptions({
  name: "FirstPage",
});
</script>

<script>
import { uid } from "quasar";
import axios from "axios";

export default {
  data() {
    return {
      dataToSend: {
        name: "",
        surname: "",
        city: "",
        email: "",
        date: "",
      },
      options: [
        "Moscow",
        "Saint Petersburg",
        "Kazan",
        "Yekaterinburg",
        "Novosibirsk",
      ],
    };
  },

  methods: {
    postData() {
      const newData = {
        id: uid(),
        name: this.dataToSend.name,
        surname: this.dataToSend.surname,
        city: this.dataToSend.city,
        email: this.dataToSend.email,
        date: this.dataToSend.date,
      };

      axios
        .post("https://jsonplaceholder.typicode.com/posts", {
          newData,
        })
        .then(function (res) {
          console.log(res);
        })
        .catch(function (error) {
          console.error(error);
        });

      this.dataToSend.name = "";
      this.dataToSend.surname = "";
      this.dataToSend.city = "";
      this.dataToSend.email = "";
      this.dataToSend.date = "";
    },
  },
};
</script>