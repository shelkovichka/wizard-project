<template>
  <div class='page'>
        <div class='form'>
            <div class='card'>
                <h2>Title of the task</h2>
                <input type='text' name='title' placeholder='Title' 
                class='doer' :value='title' @input='addTitle'>
                <p class='error' v-for='error in errors' :key='error'>
                    {{ error }}
                </p>
            </div>
        </div>
    </div>
    <div class='next' @click='checkForm'>
        <router-link :to="{name: 'description'}">Next</router-link>
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
            if (!this.title) {
                this.errors.pop();
                this.errors.push('Required field')
                return true
            }
        },
        addTitle({target}) {
            this.$store.commit('addTitle', target.value)
        }
    },
    computed: {
        title() {
            return this.$store.state.userCard.title
        }
    }
}
</script>