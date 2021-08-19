//template
<template>
    <header>
        <img id="logo" alt="Vue logo" src="../assets/logo.jpg">
        <ul id="nav">
            <li><a href="/" target="_blank">Home</a></li>
            <li><a href="/" target="_blank">All posts</a></li>
        </ul>
        <div class="button-container">
            <button id="plus-btn">➕</button>
            <button
                id="user-btn"
                v-on:click="clicker"
                >🧔</button>
        </div>
        <Dropdown :options="options" v-if="dropdownState"/>
    </header>
</template>

//script
<script>
    import Dropdown from './Dropdown.vue'

    export default {
        name: 'Header',
        props: {},
        data () {
            return {
                options: [
                    {
                        title: "My posts",
                        url: "my-posts"
                    },
                    {
                        title: "Log in",
                        url: "login"
                    }
                ],
                dropdownState: false
            }
        },
        components: {
            Dropdown
        },
        methods: {
         clicker () {
            return this.dropdownState = !this.dropdownState
        }
        }     
    }
</script>

//style
<style>
    header {
        display: flex;
        width: 100%;
        justify-content: space-between;
        border: 1px solid #ff0ff0;
    }

    #nav {
        display: flex;
        flex: 1;
        justify-content: start;
        list-style: none;
    }

    #nav > li {
        margin-left: 0.5rem;
    }

    #logo {
        width: 2rem;
        height: 2rem;
    }

    .button-container {
        display: flex;
    }

    #plus-btn, #user-btn {
        position: relative;
        border: none;
        background: lightblue;
        margin-left: 0.5rem;
    }


</style>

