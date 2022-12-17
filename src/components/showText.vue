<template>
    <p v-bind:style = "style">{{string}}</p>
</template>

<style>
    p{
        margin-left: 50px;
    }
</style>

<script>

export default{
    data:function(){
        return {
            
        }
    },
    props:['string','style']
}

</script>