
<template>
  <div>
    <p>{{ content }}</p>
  </div>
</template>

<script>
/* eslint-disable */
import axios from 'axios'
export default {
    name: 'Main',
    data() {
        return {
            content: "No content"
        }
    },
    methods: {
        getUsers(){
        const path = 'http://127.0.0.1:5000/ver_admins'
        axios.post(path).then((res) => {
            this.content = res.data
            console.log(this.content)
        })
        .catch((err) => {
            console.log(err)
        })
        }
    },
    created() {
        this.getUsers();
    },
}
</script>