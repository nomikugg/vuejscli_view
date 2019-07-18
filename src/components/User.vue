<template>
    <div class="users">
        <h1>User Components</h1>
        <ul>
            <li v-for="user in users" :key="user.id">
                
                {{user.name}} - {{user.email}}
                <button v-on:click="deleteUser(user)">X</button>
            </li> 
        </ul>
        <form action="#" v-on:submit.prevent="addUser">
            <input type="text" v-model="newUser.name" placeholder="Nombre">
            <input type="email" v-model="newUser.email" placeholder="Email">
            <button type="submit">
                Add
            </button>
        </form>
    </div>
</template>

<script>
export default {
    data(){
        return {
            users: [/*
                {
                    name:'Jose',
                    email: 'jose@me.com',
                    contacto: false
                },
                {
                    name:'Ryan',
                    email: 'ryan@me.com',
                    contacto: false
                },
                {
                    name:'Maria',
                    email: 'maria@me.com',
                    contacto: true
                },*/
            ],
            newUser:{
                
            }
        }
    },
    methods: {
        addUser(e){
            //e.preventDefault();
            //console.log("agregando usuario", this.newUser);
            this.users.push(this.newUser);
            this.newUser = {};
        },
        deleteUser(user){
            this.users.splice(this.users.indexOf(user), 1);
        }
    },
    created(){
        //console.log("componenete creado");
        //this.$http.get('https://jsonplaceholder.typicode.com/users').then(res => console.log(res));
        this.$http.get('https://jsonplaceholder.typicode.com/users').then(res => this.users = res.body);
    }
}
</script>
<style>
    .users{
        background: #333;
        color: white;
        padding: 20px;
    }
</style>
