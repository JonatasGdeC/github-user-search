<script>
    export default {
    methods: {
        toggleTheme() {
            this.$emit('toggle-theme');
        }
    }
}
</script>

<template>
    <header class="header" :class="{'modoDark' : modoDark}">
        <div class="header__top">
            <h1>devfinder</h1>
            <div @click="toggleTheme">
                <p>dark</p>
                <img src="../assets/images/moon.svg" alt="">
            </div>
        </div>
        <div class="header__search">
            <label for="search">
                <img src="../assets/images/icon-search.svg" alt="">
            </label>
            <input type="text" id="search" placeholder="Search GitHub username">
            <button>Search</button>
        </div>
    </header>
</template>

<style>
header{
    display: flex;
    flex-direction: column;
    gap: 36px;
    padding: 20px 0 24px;

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