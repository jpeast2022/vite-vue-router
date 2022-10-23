<template>
    
    <div class="page">
        <h1>Guide Components</h1>
        <p>Lorem ipsum dolor sit amet consectetu</p>
        <h2>{{ userData.title }}</h2>
        <p>
            {{ userData.bio }}
        </p>
        </div>
           
            
</template>

<script>
    import { ref } from 'vue';
    const loadUserData = async() =>{
        return new Promise((resolve)=>{
            setTimeout(()=>{
                resolve({
                    title: 'Jaypee Quintana',
                    bio: `Lorem ipsum dolor sit amet consectetur adipisicing elit. Aliquam obcaecati amet, a expedita minus delectus laborum reprehenderit at tempora pariatur qui dolore, explicabo nemo, doloremque possimus ipsa minima quibusdam quae?
                            Lorem ipsum dolor, sit amet consectetur adipisicing elit. Blanditiis repellendus officia delectus consectetur alias ipsum culpa earum error, reiciendis ab, nam velit assumenda. Minus praesentium cupiditate vel, laborum quidem debitis?
                            Lorem ipsum dolor sit amet consectetur, adipisicing elit. Natus atque architecto ut doloremque nulla tempore! Aut repellendus ipsam, officia similique modi repudiandae? Rerum ad sit quos possimus. Maiores, repudiandae. Eveniet.
                            Lorem ipsum dolor sit amet consectetur, adipisicing elit. Soluta debitis, sit maiores iste amet placeat accusantium, cumque aliquid unde provident perferendis incidunt eum magnam? Asperiores deserunt illum sapiente ipsam a`
                })
            }, 1000)
        })
    }

    export default {
    async setup() {
        const userData = ref(await loadUserData())
        return {
            userData
        }
    }
    }
</script>

<style>
    .page{
        border: 1px solid gray;
        padding: 10px;
    }
</style>
