<template>
  <li class="books" v-for="book in books" :key="book" @click="active">
      {{ book }}
  </li>
</template>

<script>
export default {
    data() {
        return {
            books: ['Home', 'About']
        }
    },
    methods: {
        active(e) {
            const books = document.querySelectorAll('.books');
            books.forEach(items => {
                items.classList.remove('active');
            })

            e.target.classList.add('active');
        }
    },
    mounted() {
        const books = document.querySelectorAll('.books');
        books[0].classList.add('active');
    }
}
</script>