<template>
    <div class="dropdown">
        <ul>
            <li
            v-for="option in options"
            :key="option.title"
            >
                <a :href="option.url">{{option.title}}</a>
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        name: 'Dropdown',
        props: {
            options: Array,
        },
    }
</script>

<style>
    .dropdown {
        position: absolute;
        top: 4rem;
        right: 0;
        width: 20rem;
        background: #FFF;
        box-shadow: -2px 3px 5px 0px rgba(0,0,0,0.75);
        -webkit-box-shadow: -2px 3px 5px 0px rgba(0,0,0,0.75);
        -moz-box-shadow: -2px 3px 5px 0px rgba(0,0,0,0.75);
        z-index: 1;
    }

    .dropdown > ul {
        list-style: none;
        line-height: 2rem;
        margin: 0;
        padding: 0;
    }

    .dropdown > ul > li {
        padding: 0.5rem 1rem;
    }

    .dropdown > ul > li:hover {
        background: #DBE2EF;
        cursor: pointer;
    }

    .dropdown > ul > li > a {
        color: #222;
        text-decoration: none;
    }    
</style>