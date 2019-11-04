<template>
    <div class="component">
        <h3>You may view the User Details here</h3>
        <p>Name: {{name}}</p>
        <p>Age: {{userAge}}</p>
        <button @click="resetName">Reset Name</button>
        <button @click="resetFn()">Reset Name Parent</button>
    </div>
</template>

<script>
    import { eventBus } from "../main";
    export default{
        props: {
            name: {
                type: String,
                default: 'Nitta'
            },
            resetFn: Function,
            userAge: Number
        },
        methods:{
            resetName(){
                this.name = 'FFF';
                this.$emit('resetwasName', this.name);
            }
        },
        created(){
            eventBus.$on("agewasEdit" ,(age) => {
                this.userAge = age;
            });
        }
    }
</script>

<style scoped>
    div {
        background-color: lightcoral;
    }
</style>
