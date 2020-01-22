<template>
  <div class="hello">
    Testing insecure https request...
  </div>
</template>

<script>
import https from 'https';

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  mounted() {
    const agent = new https.Agent({
      rejectUnauthorized: false,
    });
    this.axios.get('https://192.168.4.1/hello', {httpsAgent: agent}).then(() => {

    }).catch(() => {

    });
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
