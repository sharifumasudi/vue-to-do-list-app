<template>
    <div class="text-pink-600 mt-10 font-sans">
        <strong>{{ brand }}</strong><br>
        <span>{{ year }}</span>
    </div>
    
</template>

<script>
    export default{
        name: 'Footer',
        data() {
            return {
                brand: 'Masoud-codes Generator..',
                year: 2021,
            }
        }
    }
</script>

<style scoped>
strong{
    font-weight: bold;
}
</style>