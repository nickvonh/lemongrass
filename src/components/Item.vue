<template>
    <div class="box">
        <article class="media">
        <div class="media-content">
            <div class="content">
                <div class="level">
                    <div class="level-left">
                        <strong>{{item.name}}</strong> 
                    </div>
                    <div class="level-right">
                        <small><strong>{{item.price}}</strong></small>
                    </div>
                </div>

                <p>{{item.desc}}</p>
                
            </div>
        </div>
        </article>
    </div>
</template>

<script>

export default {
    name : "item",
    props: ['item'],
    mounted(){
        this.$refs.image.addEventListener('error', ()=>{
            this.err = true
        })
    },
    data() { 
        return {
            data : null,
            err: false
        }
    },
    computed: {
        image(){
            if(!this.err){
                return "../dist/photos/" + this.item.name.replace(/\s/g,"_").replace(/\./g,"").toLowerCase() + ".jpg"
            }
        }
    }
}
</script>
<style lang="stylus">
.box
    margin 17.5px 0
    box-shadow none
    .content
        .level
            font-size 1.3em
        p
            font-size .7em
</style>
