<template>
  <div class='page'>
        <div class='result'  data-aos="fade-bottom" data-aos-duration="500" data-aos-easing="linear">
            <div class='final'>
                <h1>{{ this.$store.state.userCard.title }}</h1>
                <p>{{ this.$store.state.userCard.description }}</p>
                <p><strong>Time to complete:</strong> {{ this.$store.state.userCard.time }}h</p>
                <p><strong>Completed by</strong> {{ this.$store.state.userCard.doer }}</p>
                <p><strong>Applications: </strong></p>
                <p v-for='app in this.$store.state.userCard.apps' :key='app'>{{ app }}</p>
            </div>
        </div>
    </div>
</template>

<script>

</script>

<style scoped>
h1 {
    text-align: center;
    font-size: 2.3rem;
}
.final {
    background-color: white;
    color: #0a1417;
    font-family: sans-serif;
}
.result {
    background-color: white;
    text-transform: none;
    padding: 0 2%;
    border: 15px double #85aac5;
    width: 50vw;
    height: auto;
}
</style>