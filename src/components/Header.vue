<script>
import axios from 'axios';

    export default {
        data() {
            return {
                darkMode: false,
                username: '',
                errorSearch: false
            };
        },
        methods: {
            toggleTheme() {
                this.$emit('toggle-theme');
                this.darkMode = !this.darkMode;
            },
            async buscarUsuario() {
                this.errorSearch = false
                try {
                    const response = await axios.get(`https://api.github.com/users/${this.username}`);
                    this.$emit('usuario-encontrado', response.data);
                    this.username = ''
                } catch (error) {
                    this.errorSearch = true
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
            <label for="search" @click="errorSearch=false">
                <img src="../assets/images/icon-search.svg"  alt="">
            </label>
            <input type="text" v-model="username" id="search" placeholder="Search GitHub username">
            <p :style="{display: errorSearch ? 'block' : 'none'}">No results</p>
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

            @media(max-width: 1024px){
                font-size: 13px;
            }
        }
    }

    .header__search{
        display: flex;
        align-items: center;
        padding: 24px 32px;
        border-radius: 15px;
        box-shadow: 0px 8px 20px rgba(0, 0, 0, 0.1);

        @media(max-width: 1024px){
            padding: 10px;
        }

        input{
            border: none;
            width: 100%;
            margin: 0 25px;
            font-size: 18px;
            font-weight: 400;

            &:focus {
                outline: none;
            }

            @media(max-width: 768px){
                font-size: 13px;
                margin: 0 9px;
            }
        }

        p{
            color: red;
            margin: 0 24px;
            white-space: nowrap;

            @media (max-width: 768px) {
                margin: 0 6px;
                font-size: 8px;
                display: inline-block;
            }
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

            @media(max-width: 768px){
                font-size: 14px;
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
            color: #fff;

            &::placeholder{
                color: #fff;
            }
        }
    }
}
</style>