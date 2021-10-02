<template>
  <li class="books" v-for="item in books" :key="item.id" @click="active">
      <router-link class="router-link" :to="{path: item.router}">
        {{ item.name }}
      </router-link>
  </li>
</template>

<script>
export default {
    data() {
        return {
            books: [
                { id: 1, name: 'Home', router: '/' },
                { id: 2, name: 'About', router: '/About' }
            ]
        }
    },
    methods: {
        active(e) {
            const books = document.querySelectorAll('.books');
            books.forEach(items => {
                items.classList.remove('active');
            })

            e.target.parentElement.classList.add('active');
        }
    }
}
</script>