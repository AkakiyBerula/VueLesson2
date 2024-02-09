<template>
    <div>
        <div class="container text-center">
            <h1 class="display-4">Personal Data</h1> 
            <p class="lead">{{ firstName }}</p> 
            <p class="lead">{{ lastName }}</p>
            <div>
                <p class="lead">Ввести ім'я</p>
                <input type="text" v-model="firstName" @input="changeFirstName($event.target.value)">
                
            </div>
            <div>
                <p class="lead">Ввести прізвище</p>
                <input type="text" v-model="lastName" @input="changeLastName($event.target.value)">
            </div>
            <error-message 
                :firstName="firstName"
                :lastName="lastName" />
            <p class="lead">{{ age }}</p>
            <div>
                <p>Змінити вік користувача</p>
                <button class="btn btn-success" @click="incrementAge">+</button>
                <button class="btn btn-danger" @click="decrementAge">-</button>
            </div>
            <p class="lead">{{ height }} cm</p>
            <p class="lead">Вага: {{ weight }} kg</p>
            <p class="lead">Індекс маси тіла: {{ countBodyMassIndex(height, weight) }}</p>
            <p class="lead">{{ filterMaxGrade }}</p>
        </div>
        <HttpRequest />
        <div class="container text-center">
            <h1 class="display-4">Other Data</h1> 
            <button class="btn btn-danger" @click="changeFriend">Змінити друга</button>
            <p class="lead">{{ friend.name }}</p> 
            <div>
                <p class="lead">Ввести ім'я друга</p>
                <input type="text" :value="friend.name" @input="friend.name = $event.target.value">
            </div>
            <p class="lead">Вік: {{ friend.age }}</p>
            <div>
                <p>Змінити вік друга користувача</p>
                <button class="btn btn-success" @click="incrementFriendAge">+</button>
                <button class="btn btn-danger" @click="decrementFriendAge">-</button>
            </div>
            <p class="lead">Ріст: {{ friend.height }} cm</p>
            <p class="lead">Вага: {{ friend.weight }} kg</p>
            <p class="lead">Індекс маси тіла: {{ countBodyMassIndex(friend.height, friend.weight) }}</p>
            <p class="lead">Друзі: {{ friend.friendsList }}</p>
            <div>
                <button class="btn btn-primary" @click="filterFriendsList('Jack')">Відфільтрувати друзів</button>
            </div>
        </div>
        <div>
            <p>{{ combinedData }}</p>
        </div>
    </div>
    
</template>

<script>
import ErrorMessage from './ErrorMessage.vue'
import HttpRequest from './HttpRequest.vue'

export default {
    name: 'Data',
    components: {
        ErrorMessage,
        HttpRequest
    },
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
                friendsList: ['Jill', 'Jane', 'Jack', 'Joseph']
            },
            reportCard: [
                {subject: "Math", grade: 4},
                {subject: "English", grade: 5},
                {subject: "Science", grade: 4},
                {subject: "History", grade: 4},
                {subject: "Geography", grade: 5},
                {subject: "Physical education", grade: 3},
                {subject: "Art", grade: 3},
                {subject: "Music", grade: 5} 
            ],
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
            this.friend.age--
        },
        changeFirstName(newFirstName) {
            this.firstName = newFirstName;
        },
        changeLastName(newLastName) {
            this.lastName = newLastName;
        },
        filterFriendsList(name) {
            this.friend.friendsList = this.friend.friendsList.filter(friend => friend === name);
        },
        changeFriend() {
            let newFriend = {
                name: 'Otto',
                age: 42,
                height: 185,
                weight: 82,
                friendsList: ['Ferdinand', 'Astrid', 'Cody']
            }
            this.friend = newFriend
        },
        countBodyMassIndex(height, weight) {
            return weight / ((height / 100) ** 2)
        }
    },
    computed: {
        filterMaxGrade() {
            return this.reportCard.filter(item => item.grade === 5);
        }
    }
}

</script>


<style scoped>


</style>