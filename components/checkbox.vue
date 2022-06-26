<template>
    <div class="checkbox-wrap">
        <input @change="handleChange(data)" type="checkbox" :value="data"/>
        <label>{{data}}</label>
    </div>
</template>

<script>
export default{
    props: {
        data: [String, Object]
    },
    methods: {
        handleChange(value){
            this.$emit('input', value)
        }
    }
}
</script>

<style>
.checkbox-wrap{
    border: 1px solid red;
    margin-bottom: .5em;
    padding: .5em;
}
</style>