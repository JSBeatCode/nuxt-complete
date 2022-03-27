<template>
    <div>
        <h4 class = "display-4">To Do List</h4>
        <div class="alert alert-dart">
            <ul class = "nav">
                <li class = "nav-item">
                    <nuxt-link to = "/" class = "nav-link">Home</nuxt-link>
                </li>
                <li class = "nav-item">
                    <nuxt-link to = "/lists" class = "nav-link">Lists</nuxt-link>
                </li>
                <li class = "nav-item">
                    <nuxt-link to = "/about" class = "nav-link">About</nuxt-link>
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'AppHeader'
    }
</script>
