<template>
    <div class="component">
        <h1>The User Component</h1>
        <p>I'm an awesome User!</p>
        <hr>
        <button @click="changeName">
            change user
        </button>
        <div class="row">
            <div class="col-xs-12 col-sm-6">
                <!-- v-bind:name="name" parameter passed to the child -->
                <!-- @resetname is in child that resets name  -->
                <app-user-detail :name="name" @resetname="name = $event"></app-user-detail>
            </div>
            <div class="col-xs-12 col-sm-6">
                <app-user-edit></app-user-edit>
            </div>
        </div>
    </div>
</template>

<script>
    import UserDetail from './UserDetail.vue';
    import UserEdit from './UserEdit.vue';

    export default {
        data:function(){
            return{
                name:'sala'
            };
        },
        methods:{
            changeName(){
                this.name = 'sowmy'
            }
        },
        components: {
            appUserDetail: UserDetail,
            appUserEdit: UserEdit
        }
    }
</script>

<style scoped>
    div {
        background-color: lightblue;
    }
</style>
