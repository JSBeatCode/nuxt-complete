<template>
    <nuxt-link :to="'lists/'+id">
        <div class="list">
            <p>{{list.title}}</p>
        </div>
    </nuxt-link>
</template>

<script>
    export default {
        name: "OnePage",
        props: ["list", "id"]
    }
</script>
