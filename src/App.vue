<template>
  <main class="container">
    <div class="row py-3">
      <div class="col-10"></div>
      <div class="col-2">
        <select class="form-control" @change="change($event.target.value)">
          <option value="en">English</option>
          <option value="de">Deutsch</option>
        </select>
      </div>
    </div>

    <div class="row">
      <div class="col-md-12">
        <h2>This text is translated in the frontend.</h2>
        <p>{{ text }}</p>

        <button class="btn btn-outline-primary">Like</button>
      </div>
    </div>
  </main>
</template>

<script lang="ts">
import {defineComponent} from 'vue';
import axios from 'axios';

export default defineComponent({
  name: 'App',
  setup() {
    const {t, locale} = useI18n();

    return {t, locale};
  },

  data() {
    return {
      text: '',
      lang: 'en'
    }
  },

  async mounted() {
    await this.load();
  },

  methods: {
    async load(){
      axios.defaults.headers['Accept-Language'] = this.lang;
      const response = await axios.get('http://localhost:8000/text');
      this.text = response.data.text;
    },

    async change(lang: string) {
      this.lang = lang;
      await this.load()
    }
  }

});
</script>
