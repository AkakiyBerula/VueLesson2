<template>
    <div class ="container text-center">
        <h3 class="display-4">Http Request</h3>
        <p class="lead">{{ combinedData }}</p>
    </div>

</template>

<script>

export default {
    name: 'HttpRequest',
    data() {
        return {
            reactiveData: [],
            httpData: [],
            loading: true
        }
    },
    methods: {
        fetchData() {
            this.combinedDataLoading = true;
            setTimeout(() => {
            this.httpData = [
                    { id: 1, name: "Heroes of Might and Magic 3" },
                    { id: 2, name: "Cossacks: Back to War" },
                    { id: 3, name: "Civilization IV"}
                ];
                this.combinedDataLoading = false;
            }, 2000);
        }
    },
    created() {
        this.fetchData();
    },
    computed: {
        combinedData() {
            return this.reactiveData.concat(this.httpData);
        }
    }
    
}

</script>


<style scoped>


</style>