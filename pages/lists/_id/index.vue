<template>
    <div>
        <nuxt-link to="/lists">Back to Lists</nuxt-link>
        <h2>{{list.title}}</h2>
        <hr>
        <small>List ID : {{list.id}}</small>
    </div>
</template>

<script>
import axios from 'axios';
    export default {
        data () {
            return {
                list: {}
            }
        },
        async created() {
            const config = {
                headers: {
                    Accept: 'application/json'
                }
            };

            try {
                const res = await axios.get(`https://jsonplaceholder.typicode.com/todos/${this.$route.params.id}`, config);
                this.list = res.data;
            } catch (err) {
                console.log(err);
            }
        },
        head() {
            return {
                title: this.list,
                meta: [
                    {
                        hid: 'description',
                        name: 'name',
                        content: 'content'
                    }
                ]
            }
        }
    }
</script>
