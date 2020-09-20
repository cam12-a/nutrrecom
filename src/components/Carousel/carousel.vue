<template>
    <div>
        <slot>
        </slot>
    </div>
</template>
<script>
export default {
     el:'.Body',
    data() {
        console.log(this.$children)
        return {
            index:0,
            slides:[]
        }
    },
    mounted() {
        this.slides=this.$children
        this.slides.forEach((slide,i) =>{
            slide.index=i
        })
    }
}
</script>