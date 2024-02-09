<template>
    

</template>

<script>

export default {
    name: 'SendAPI',
    props: ['data'],
    data() {
        return {
            reactiveData: [],
            httpData: [],
            loading: true
        }
    },
    methods: {
        fetchData(data) {
            console.log('Виконання API запиту з даними: ', data);
            // далі має відбутись відправка API
            
        }
    },
    watch: {
        data(newValue, oldValue) {
            console.log(newValue, oldValue)
            this.fetchData(newValue)
        }
    }
}

</script>


<style scoped>


</style>