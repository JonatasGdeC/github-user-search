<script>
import './CardUser.scss'
</script>

<template>
    <div class="card">
        <aside>
            <img src="../assets/images/img-cat.png" alt="">
        </aside>
        <div>
            <div class="header">
                <h2>The Octocat</h2>
                <p>Joined 5 Jan 2011</p>
            </div>
            <p class="username">@octocat</p>
            <p class="description">Lorem ipsum dolor sit amet consectetur adipisicing elit. Natus maxime, beatae laboriosam libero unde necessitatibus rerum ipsa doloribus molestiae laborum perspiciatis veritatis dolorum repudiandae recusandae iusto corrupti culpa, iure nulla.</p>
            <ul>
                <li>
                    <p class="info">Repos</p>
                    <p class="number">8</p>
                </li>
                <li>
                    <p class="info">Followers</p>
                    <p class="number">3938</p>
                </li>
                <li>
                    <p class="info">Following</p>
                    <p class="number">9</p>
                </li>
            </ul>
            <div class="moreInfos">
                <div>
                    <img src="../assets/images/location.svg" alt="">
                    <p>San Francisco</p>
                </div>
                <div>
                    <img src="../assets/images/twiter.svg" alt="">
                    <p>Not Available</p>
                </div>
                <div>
                    <img src="../assets/images/copy.svg" alt="">
                    <p>https://github.blog</p>
                </div>
                <div>
                    <img src="../assets/images/companye.svg" alt="">
                    <p>@github</p>
                </div>
            </div>
        </div>
    </div>
</template>