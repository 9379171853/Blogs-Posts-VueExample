<template>
    <div id="all-freinds">
        <h2>All Freinds </h2>
    <div v-for ="(friend, index) in friends" :key="index">
        <span @click="unfriend(friend.name)"> {{friend.name}}</span> 
    </div>
    </div>
</template>

<script>
export default {
    name: 'AllFreinds',
    props : ['friends'],
    data() {
        return {
            // Now i am going to resuablity by putting on parrent component one place..
            // friends: [
            //     {name : 'Atul', online: true},
            //     {name : 'Sunil', online: false},
            //     {name : 'Raghu', online: true},
            //     {name : 'Shyam', online: false},
            // ]
        }
    },
    methods:{
        unfriend(name){
            this.$emit('delete', { name })
        }
    }
}
</script>

<style>

</style>