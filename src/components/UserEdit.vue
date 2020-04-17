<template>
    <div class="component">
        <h3>You may edit the User here</h3>
        <p>Edit me!</p>
        <p> User name {{name}} </p>
        <button @click='editName'>edit name</button>
    </div>
</template>

<script>
    import {eventBus} from '../main';
    export default{
        props:['name'],
        methods:{
            editName(){
                this.name = 'sowmy';
                // triggers event on parent
                // this.$emit('nameChanged',this.name);

                // triggers event in main.js file
                eventBus.$emit('nameChanged',this.name);
            }
        }
    }
</script>

<style scoped>
    div {
        background-color: lightgreen;
    }
</style>
