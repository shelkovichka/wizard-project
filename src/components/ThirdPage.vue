<template>
  <div class='page'>
        <div class='form'>
            <div class='card'>
                <h2>Time to complete: (in hours)</h2>
                <input type='number' class='doer' placeholder='Time' 
                name='time' :value='time' @input='addTime'>
                <p class='error' v-for='error in errors' :key='error'>{{ error }}</p>
            </div>
        </div>
        <div class='back'>
            <router-link :to="{name: 'description'}">Back</router-link>
        </div>
        <div class='next'>   
            <router-link :to="{name: 'doer'}" @click='checkForm'>Next</router-link>
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return {
            errors: []
        }
    },
    methods: {
        checkForm() {
            if (this.time < 1 || this.time > 100) {
                this.errors.pop();
                this.errors.push('The value must be between 1 and 100')
                return true;
            }
        },
        addTime({target}) {
            this.$store.commit('addTime', target.value)
        }
    },
    computed: {
        time() {
            return this.$store.state.userCard.time
        }
    }
}
</script>