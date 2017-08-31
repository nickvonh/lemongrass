<template>
    <div class="container">
        <h1 class="title">{{title}}</h1>
        <div v-for="(each, key) in menu" :key="key">
            <item :item="each"></item>
        </div>
    </div>
</template>

<script>
import Item from './Item.vue'
export default {
    name : "menuBlock",
    props: ['menu', 'title'],
    components: {Item},
    data() { 
        return {
            data : null
        }
    }
}
</script>
