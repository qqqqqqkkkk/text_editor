<template>
    <textarea name="" id="" cols="55" rows="8" v-model = "page" v-on:input="change"></textarea>
</template>

<style>
    textarea{
        border:2px solid black;
        box-shadow:13px 6px 3px rgb(86, 86, 167);
    }
</style>

<script>

export default{
    data:function(){
        return {
            page:''
        }
    },
    methods:{
        change:function(){
            this.$emit('hh',this.page);
        }
    },
    
}

</script>