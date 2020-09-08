<template>
  <section>
    <h1>{{ title }}</h1>
    <p>{{ message }}</p>
    <pre class="text-light bg-dark">{{ html_data }}</pre>
  </section>
</template>

<script>

const axiosObj = require('axios');
//テスト用ダミーJSON;
let url = "https://jsonplaceholder.typicode.com/posts";


export default {
  data: function() {
    return {
      title:'Axios',
      message:'this page is test of axios.'
    };
  },
  asyncData: async function() {
    let result = await axiosObj.get(url);
    return { html_data: result.data};
  }
}
</script>