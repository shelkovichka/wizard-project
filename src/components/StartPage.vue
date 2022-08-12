<template>
    <div class='page'>
        <div class='start'>
            <router-link :to="{name: 'title'}">Create a task!</router-link>
        </div>
    </div>
</template>

<style scoped>
.start {
    text-align: center;
    background-color: #85aac5;
    padding: 5%;
    width: 35%;
}

.start a {
    background-color: #85aac5;
    font-family: sans-serif;
    font-size: 1.5rem;
    text-decoration: none;
    text-transform: uppercase;
    color: white;
}
</style>