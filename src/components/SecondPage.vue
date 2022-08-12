<template>
  <div class='page'>
        <div class='form'>
            <div class='card'>
                <h2>Description of the task</h2>
                <input type='text' class='doer' name='description' placeholder='Description'
                :value="description" @input="addDescription">
                <p class='error' v-for='error in errors' :key='error'>{{ error }}</p>
            </div>
        </div>
        <div class='back'>
            <router-link :to="{name: 'title'}">Back</router-link>
        </div>
        <div class='next'>
            <router-link :to="{name: 'time'}" @click='checkForm'>Next</router-link>
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
            if (!this.description) {
                this.errors.pop();
                this.errors.push('Required field')
                return true;
            }
        },
        addDescription({target}) {
            this.$store.commit('addDescription', target.value)
        }
    },
    computed: {
        description() {
            return this.$store.state.userCard.description
        }
    }
}
</script>