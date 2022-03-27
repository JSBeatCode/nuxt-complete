<template>
    <div>
        <form @submit.prevent="onSubmit" class = "row g-3">
            <div class = "input-group mb-3 col-auto">
                <input type = "text" class = "form-control" v-model="text" placeholder="Search Lists..." />
                <input type = "submit" class = "btn btn-outline-secondary" id = "button-addon2" value = "Search Lists"/>
            </div>
        </form>
    </div>
</template>

<script>
    export default {
        name: 'SearchLists',
        data() {
            return {
                text: ''
            };
        },
        methods: {
            onSubmit() {
                this.$emit('search-text', this.text);
                this.text = "";
            }
        }
    }
</script>
