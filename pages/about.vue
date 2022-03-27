<template>
    <div>
        <h1>About Page</h1>
        <p>This is About Page</p>
    </div>
</template>

<script>
    export default {
        head() {
            return {
                title: 'About Page',
                meta: [
                    {
                        hid: 'description',
                        name:'name',
                        content: 'about this page'
                    }
                ]
            }
        }
    }
</script>
