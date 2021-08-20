<template>
    <h2>{{ title }}</h2>
    <form v-on:submit.prevent>
        <input type="text"/>
        <input type="password"/>
        <button @click="authType.callBack">{{ authType.title }}</button>
    </form>
</template>

<script>
    export default {
        name: 'Login',
        props: {
            authType: {
                title: String,
                callBack: Function
            }
        }
    }
</script>

<style scoped>
</style>