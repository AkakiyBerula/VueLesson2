<template>
    <div>
        <div class="container text-center">
            <h1 class="display-4">Personal Data</h1> 
            <p class="lead">{{ firstName }}</p> 
            <p class="lead">{{ lastName }}</p>
            <p class="lead">{{ age }}</p>
            <p class="lead">{{ height }} cm</p>
            <p class="lead">{{ weight }} kg</p>
        </div>
        <div class="container text-center">
            <h1 class="display-4">Other Data</h1> 
            <p class="lead">{{ friend.name }}</p> 
            <p class="lead">{{ friend.age }}</p>
            <p class="lead">{{ friend.height }} cm</p>
            <p class="lead">{{ friend.weight }} kg</p>
            <p class="lead">{{ friend.friendsList }}</p>
        </div>
    </div>
    
</template>

<script>

export default {
    name: 'Data',
    data() {
        return {
            count: 0,
            firstName: "John",
            lastName: "Doering",
            age: 29,
            height: 180,
            weight: 78,
            friend: {
                name: "Janna",
                age: 30,
                height: 168,
                weight: 70,
                friendsList: ["Jane", "Jack", "Jill", "Joseph"]
            }
        }
    },
    
}

</script>


<style scoped>


</style>