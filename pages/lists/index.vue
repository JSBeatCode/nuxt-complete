<template>
    <div>
        <SearchLists v-on:search-text="searchText" />
        <OnePage v-for="list in lists" :key="list.id" :id="list.id" :list="list"/>
    </div>
</template>

<script>
import axios from 'axios'
import SearchLists from '../../components/SearchLists.vue';
import OnePage from '../../components/OnePage.vue';

    export default {
        components: {
            SearchLists,
            OnePage            
        },
        data() {
            return {
                lists: []
            }
        },
        async created() {
            const config = {
                headers: {
                    Accept: 'application/json'
                }
            }

            try {
                const res = await axios.get('https://jsonplaceholder.typicode.com/todos', config)
                this.lists = res.data;
            } catch(err) {
                console.log(err)
            }
        },
        methods: {
            async searchText(text) {
                const config = {
                    headers: {
                        Accept: 'application/json'
                    }
                }
                try {
                    const res = await axios.get('https://jsonplaceholder.typicode.com/todos', config)
                    const findLists = res.data;

                    this.lists = findLists.filter(one => one.title.includes(text));
                } catch(err) {
                    console.log(err)
                }
            }
        },
        head () {
            return {
                title: 'Todo List',
                meta: [
                    {
                        hid: 'description',
                        name: 'name',
                        content: 'Main Page'
                    }
                ]
            }
        }
    }
</script>
