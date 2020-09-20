<template>
    <div>
        Index: {{index}}
        Visible: {{visible}}
        <slot>
        </slot>
    </div>
</template>
<script>
export default {
    el:'.Body',
    data()
    {
        return {
            index:0
        }
    }, 
    computed: {
        visible(){
            return this.index===this.$parent.index
        }
    }
}
</script>