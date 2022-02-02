<template>
  <div>
    <!-- {{ number }} -->
    <p>{{ user.username }}</p>
    <p>{{ post.title }}</p>
    <p>{{ loading }}</p>
  </div>
</template>


<script>
// Ref
// import { ref } from 'vue'
// export default {
//   setup() {
//     const number = ref(0);
//     setInterval(() => {
//       number.value++;
//     }, 3000);    

//     return {
//       number
//     }
//   }
// }
import {reactive, toRefs} from 'vue'
export default {
  setup() {
    // const loading = ref(false)
    const state = reactive({
      loading: false,
      user: {
        name: "Alfa",
        username: "masmasakhirzaman"
      },
      post: {
        title: "Title",
        body: "Body"
      }
    });

    setTimeout(() => {
      state.loading = true
      // loading.value = true
      state.user.username = "AlfaRiza"
      state.post.title = "Title[update]"
    }, 5000)

    return {
      ...toRefs(state)
    }
  }
}
</script>