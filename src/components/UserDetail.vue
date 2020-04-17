<template>
    <div class="component">
        <h3>You may view the User Details here</h3>
        <p>Many Details</p>
        <h2>user Name {{swapname()}}</h2>
        <button @click="resetName">Reset name</button>
    </div>
</template>

<script>
import { eventBus } from '../main';
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
    },
    // passing parameter b/w child w/o parent
    created(){
        eventBus.$on('nameChanged',(name) => {
            this.name = name;
        })
    }
}
</script>

<style scoped>
    div {
        background-color: lightcoral;
    }
</style>
