<template>
    <div class="component">
        <h3>You may view the User Details here</h3>
        <p>Many Details</p>
        <h2>user Name {{swapname()}}</h2>
        <button @click="resetName">Reset name</button>
    </div>
</template>

<script>
export default{
    // can also be an object
    // props : ['name']
    props :{
        // propname : [data types]
        name : [String,Array]
    },
    methods:{
        swapname(){
            return this.name;
        },
        resetName(){
            this.name = 'sala';
            // emit allows to send data back to parent
            // first param is the event name,second param is the data passed through event (accessed through $ sign)
            this.$emit('resetname',this.name);
        }
    }
}
</script>

<style scoped>
    div {
        background-color: lightcoral;
    }
</style>
