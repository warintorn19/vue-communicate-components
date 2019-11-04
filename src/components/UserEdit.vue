<template>
    <div class="component">
        <h3>You may edit the User here</h3>
        <p>userAge: {{ userAge }}</p>
        <button @click="editAge">Edit Age</button>
    </div>
</template>

<script>
import { eventBus } from "../main";
export default{
    props: ['userAge'],
    methods:{
        editAge(){
            this.userAge = 15;
            eventBus.changeAge(this.userAge);
            // eventBus.$emit("agewasEdit", this.userAge);
        }
    }
}
</script>

<style scoped>
    div {
        background-color: lightgreen;
    }
</style>
