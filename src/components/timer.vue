<template>
    <div id="timer">
        
        <img :src="`${image}`" />
    </div>
</template>

<script>
export default {
    name: "timer",
    data() {
        return {
            answer: {},
            image: {},
            timer: "",
            //image: this.answer.image,
        };
    },
    created(){
        this.fetchData();
        this.timer = setInterval(this.fetchData, 5000);
    },
    methods: {
        async fetchData(){
            const res = await fetch("https://yesno.wtf/api");
            const data = await res.json();
            this.answer = data;
            this.image=data.image;
        },
        cancelAutoUpdate(){
            clearInterval(this.timer);
        },
    },
    beforeUnmount(){
        this.cancelAutoUpdate();
    },    
};
</script>