<script setup>
import './Header.scss'
</script>

<template>
    <header class="header">
        <div class="header__top">
            <h1>devfinder</h1>
            <div>
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