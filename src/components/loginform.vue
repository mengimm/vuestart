<template>
    <div id="loginform">
        <form @submit.prevent="login">
            <input v-model="username" placeholder="логин">
            <input v-model="password" placeholder="пароль" type="password">
            <input type="submit" value="вход">
        </form>
    </div>
</template>

<script>
export default {
    name: "loginform",
    data(){
        return {
            username: "",
            password: ""
        };    
    },
    methods: {
        async login() {
            const {username,password}=this;
            const res = await fetch(
                "https://SomberHandsomePhysics--five-nine.repl.co/login",
                {
                    method: "POST",
                    headers: {
                        "Content-Type": "application/json"
                    },
                    body:JSON.stringify({username,password})
                }
            );
            const data = await res.json();
            console.log(data);
        }
    }
};    
</script>
