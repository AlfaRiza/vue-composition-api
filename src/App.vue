<template>
  <div>
    <button @click="decrement">-</button>
    {{ number }}
    <!-- <p>{{ user.username }}</p>
    <p>{{ post.title }}</p>
    <p>{{ loading }}</p> -->

    <button @click="increment">+</button>
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

// Reactive, toRefs
// import {reactive, toRefs} from 'vue'
// export default {
//   setup() {
//     // const loading = ref(false)
//     const state = reactive({
//       loading: false,
//       user: {
//         name: "Alfa",
//         username: "masmasakhirzaman"
//       },
//       post: {
//         title: "Title",
//         body: "Body"
//       }
//     });

//     setTimeout(() => {
//       state.loading = true
//       // loading.value = true
//       state.user.username = "AlfaRiza"
//       state.post.title = "Title[update]"
//     }, 5000)

//     return {
//       ...toRefs(state)
//     }
//   }
// }

// work with method using reusable function
import {ref} from 'vue'
import useCounter from './helpers/counter.js'
export default {
  setup() {
    const number = ref(0);

    const {increment, decrement} = useCounter(number);

    return {
      number, increment, decrement
    }
  }
}
</script>