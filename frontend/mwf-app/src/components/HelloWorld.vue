<template>
<div>
<article v-for="(fed, idx) in federations" :key="idx">
<h1>{{ fed.name }}</h1>
</article>
</div>
</template>

<script>
import { db } from '../main'
export default {
  name: 'HelloWorld',
  data () {
    return {
      federations: []
    }
  },
  firestore () {
    return {
      federations: db.collection('federations').orderBy('name')
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
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
