<template>
    <div>
        <div class="container text-center">
            <h1 class="display-4">Personal Data</h1> 
            <p class="lead">{{ firstName }}</p> 
            <p class="lead">{{ lastName }}</p>
            <div>
                <p class="lead">Ввести ім'я</p>
                <input type="text" :value="firstName" @input="firstName = $event.target.value">
                
            </div>
            <div>
                <p class="lead">Ввести прізвище</p>
                <input type="text" :value="lastName" @input="lastName = $event.target.value">
            </div>
            <p class="lead">{{ age }}</p>
            <div>
                <p>Змінити вік користувача</p>
                <button class="btn btn-success" @click="incrementAge">+</button>
                <button class="btn btn-danger" @click="decrementAge">-</button>
            </div>
            <p class="lead">{{ height }} cm</p>
            <p class="lead">{{ weight }} kg</p>
        </div>
        <div class="container text-center">
            <h1 class="display-4">Other Data</h1> 
            <p class="lead">{{ friend.name }}</p> 
            <div>
                <p class="lead">Ввести ім'я друга</p>
                <input type="text" :value="friend.name" @input="friend.name = $event.target.value">
            </div>
            <p class="lead">{{ friend.age }}</p>
            <div>
                <p>Змінити вік друга користувача</p>
                <button class="btn btn-success" @click="incrementFriendAge">+</button>
                <button class="btn btn-danger" @click="decrementFriendAge">-</button>
            </div>
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
    methods: {
        incrementAge () {
            this.age++
        },
        decrementAge () {
            this.age--
        },
        incrementFriendAge () {
            this.friend.age++
        },
        decrementFriendAge () {
            this.age--
        },
    },
}

</script>


<style scoped>


</style>