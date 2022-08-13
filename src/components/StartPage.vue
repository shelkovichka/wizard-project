<template>
    <div class='page'>
        <router-link :to="{name: 'title'}">
            <p>Create a task!</p>
        </router-link>
    </div>
</template>

<style scoped>
a {
    text-align: center;
    background-color: #85aac5;
    padding: 5%;
    width: 35%;
    text-decoration: none;
}
p {
    background-color: #85aac5;
    font-family: sans-serif;
    font-size: 1.5rem;
    text-decoration: none;
    text-transform: uppercase;
    color: white;
}
a:hover, a:hover p {
    background-color: #0f1427;
}
</style>