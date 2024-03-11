<script>
import axios from 'axios';

    export default {
        data() {
            return {
                darkMode: false,
                username: ''
            };
        },
        methods: {
            toggleTheme() {
                this.$emit('toggle-theme');
                this.darkMode = !this.darkMode;
            },
            async buscarUsuario() {
                try {
                    const response = await axios.get(`https://api.github.com/users/${this.username}`);
                    this.$emit('usuario-encontrado', response.data);
                } catch (error) {
                    console.error('Erro ao buscar usuário:', error);
                }
            }
        }
}
</script>

<template>
    <header class="header" >
        <div class="header__top">
            <h1>devfinder</h1>
            <div @click="toggleTheme">
                <p :style="{ display: darkMode ? 'none' : 'block' }">dark</p>
                <img src="../assets/images/moon.svg" :style="{ display: darkMode ? 'none' : 'block' }" alt="Thema">
                <p :style="{ display: darkMode ? 'block' : 'none' }">light</p>
                <img src="../assets/images/sun.svg" :style="{ display: darkMode ? 'block' : 'none' }" alt="Thema">
            </div>
        </div>
        <div class="header__search">
            <label for="search">
                <img src="../assets/images/icon-search.svg"  alt="">
            </label>
            <input type="text" v-model="username" id="search" placeholder="Search GitHub username">
            <button @click="buscarUsuario">Search</button>
        </div>
    </header>
</template>

<style>
header{
    display: flex;
    flex-direction: column;
    gap: 36px;
    padding: 20px 0 24px;
    transition: all ease 0.7s;

    .header__top{
        display: flex;
        align-items: center;
        justify-content: space-between;

        h1{
            font-size: 26px;
            font-weight: bold;
        }

        div{
            display: flex;
            align-items: center;
            gap: 16px;
            opacity: 0.7;
            cursor: pointer;

            p{
                font-size: 16px;
                font-weight: bold;
                text-transform: uppercase;
            }

            &:hover{
                opacity: 1;
            }
        }
    }

    .header__search{
        display: flex;
        align-items: center;
        padding: 24px 32px;
        border-radius: 15px;
        box-shadow: 0px 8px 20px rgba(0, 0, 0, 0.1);

        input{
            border: none;
            width: 100%;
            margin: 0 25px;
        }

        button{
            padding: 12px 24px;
            font-size: 16px;
            font-weight: bold;
            color: #fff;
            background-color: #0079FF;
            border: none;
            border-radius: 10px;
            transition: all ease 0.3s;
            cursor: pointer;

            &:hover{
                opacity: 0.7;
            }
        }
    }
}

.dark-header{
    color: #fff;
    .header__search{
        background-color: #1E2A47;

        input{
            background-color: #1E2A47;
        }
    }
}
</style>