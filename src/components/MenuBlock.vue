<template>
    <div class="container">
        <h3 class="sub-title">{{title}}</h3>
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
