<template>
  <div>
    <ul>
      <li v-for="(item, index) in books" :key="index">
        {{ item.title }}：{{ item.price }}
      </li>
    </ul>
  </div>
</template>

<script>
import gql from 'graphql-tag';

let query = gql(`
  query {
    books {
      title
      price
    }
  }
`)

export default {
  name: 'app',
  apollo: {
    books: {
      query
    }
  }
}
</script>