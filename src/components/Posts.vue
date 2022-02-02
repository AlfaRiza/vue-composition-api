<template>
    <div>
        <ul>
            <li v-for="post in posts" :key="post.id">{{ post.title }}</li>
        </ul>
    </div>
</template>

<script>
import axios from 'axios'
import {onMounted, ref} from 'vue'
export default {
    setup() {
        const posts = ref([]);

        const getPost = async () => {
            let response = await axios.get('https://jsonplaceholder.typicode.com/posts')
            posts.value = response.data.slice(1, 10)
        }

        onMounted(() => {
            getPost()
        })

        return {
            posts
        }
    }
}
</script>