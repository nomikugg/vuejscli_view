<template>
    
    <div class="test">
        <div v-html="myHtml"></div>
        <div v-if="showName">
            <p>
                No me pueden ver
            </p>
        </div>
        <div v-else>
            <p>
                Esta ves si no me pueden ver
            </p>
        </div>
        <hr/>
        
        <ul>
            <li v-for="task in tasks" :key="task.id">
                {{task.title}}
            </li>
        </ul>
        <input type="text" v-model="user.firstName">
        <button v-on:click="saludar(user.firstName)">
            CLICK ME!
        </button>
        <hr>
        <input type="text" v-on:keyup.enter="typedEnter">
        <br>
        {{fullName}}
        <br>
        {{msg}}
    </div>
</template>

<script>
    export default {
        data(){
            return {
                title: "Hola",
                user: {
                    firstName: "Luis",
                    lastName: "Rojas"
                },
                myHtml: "<h3>Esto es la ostia</h3>",
                showName: false,
                tasks: [
                    {title :'eat'},
                    {title: 'work'},
                    {title: 'run'}
                ]
            }
        },
        methods:{
            saludar(name){
                alert("Hello " + name)
            },
            typing(e){
                console.log(e.target.value);
            },
            typedEnter(){
                console.log("Dio un enter");
            }
        },

        computed: {
            fullName(){
                return this.user.firstName + ' '+this.user.lastName;
            }
        },
        props:{
            msg:{
                type: String,
                default: "Mensaje por defecto"
            }
        }
    }
</script>

<style media="screen">
    .test{
        background: #eeee;
    }
</style>
