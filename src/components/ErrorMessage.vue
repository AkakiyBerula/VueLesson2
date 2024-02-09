<template>
    <div>
        <h2>{{ validateLatin() }}</h2>
    </div>
</template>

<script>
export default {
    name: 'ErrorMessage',
    props: ['firstName', 'lastName'],
    data() {
        return {
            message: '',
        }
    },
    methods: {
        validateLatin() {
            const englishLettersRegex = /^[a-zA-Z]+$/;
            if (!englishLettersRegex.test(this.firstName) || !englishLettersRegex.test(this.lastName)) {
                return  'Неправильно введені ім\'я і прізвище'
            } else {
                return 'Дані введені вірно';
            }
        }
    }
    
}
</script>

<style scoped>
</style>
