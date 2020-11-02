<template>
  <div>
    <p>{{msg}}</p>
    <p>Has Published Books:</p>
    <span>{{publishedBook}}</span>
    <p>{{publishedBookMessage()}}</p>
    <p>{{fullname}}</p>
    <p>{{fullname = 'Win Lwin Oo'}}</p>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  data() {
    return {
      author: {
        name: "John Doe",
        books: [
          'Vue 2 - Advanced Guide',
          'Vue 3 - Basic Guide',
          'Vue 4 - The Mystery',
          'Vue 5 - The Mystery'
        ]
      },
      firstName: 'Hnin',
      lastName: 'Cherry'
    }
  },
  computed: {
    publishedBook() {
      return this.author.books.length > 0 ? 'Yes' : 'No'
    },
    fullname: {
      get() {
        return this.firstName + ' ' + this.lastName
      },
      set(newValue) {
        const names = newValue.split(' ')
        this.firstName = names[0]
        this.lastName = names[names.length-1]
      }
    }
  },
  methods: {
    publishedBookMessage() {
      return this.author.books.length > 3 ? 'Yes' : 'No'
    }
  }
}
</script>

<style scoped>

</style>
