<template>
    <div id="online-freinds">
        <h2>Online Freinds </h2>
        <div v-for ="(friend, index) in friends" :key="index"><span v-if="friend.online" > {{friend.name}}</span> </div>
    </div>
</template>

<script>
export default {
    name: 'OnlineFreinds',
    //passing data from parent to child using props.
    props: ['friends'],
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
    }
}
</script>

<style>

</style>