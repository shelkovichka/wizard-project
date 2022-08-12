<template>
  <div class='page'>
        <div class='form'>
            <div class='card'>
                <h2>Performer</h2>
                <select @input='addDoer' :value='doer'>
                    <option v-for='doer in doers' :key='doer'>
                        {{ doer.name }}
                    </option>
                </select>
                <p class='error' v-for='error in errors' :key='error'>{{ error }}</p>
            </div>
        </div>
        <div class='back'>
        <router-link :to="{name: 'time'}">Back</router-link>
        </div>
        <div class='next'>   
        <router-link :to="{name: 'apps'}" @click='checkForm'>Next</router-link>
        </div>
    </div>

</template>

<script>
export default {
    data(){
        return {
            doers: [
                {id: 1, name: 'Mary'}, 
                {id: 2, name:'Nick'}, 
                {id: 3, name:'Ann'}, 
                {id: 4, name:'Adam'}
            ],
            errors: []
        }
    },
    methods: {
        checkForm() {
            if (!this.doer) {
                this.errors.pop();
                this.errors.push('Select a performer')
                return true;
            }
        },
        addDoer({target}) {
            this.$store.commit('addDoer', target.value)
        }
    },
    computed: {
        doer() {
            return this.$store.state.userCard.doer
        }
    }
}
</script>

<style scoped>
select {
    border: 2px solid #0a1417;
    margin-top: 10%;
    height: 4.9vh;
    width: 20.8vw;
    border-radius: 5px;
}

select:focus {
    outline: none;
    border: 2px solid #85aac5;
}
</style>