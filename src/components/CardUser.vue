<script>
export default {
    props: {
        usuario: Object
    }
}
</script>

<template>
    <div class="card" v-if="usuario">
        <aside>
            <img :src='usuario.avatar_url' alt="">
        </aside>
        <div>
            <div class="header">
                <h2>{{ usuario.name }}</h2>
                <p>Joined 5 Jan 2011</p>
            </div>
            <p class="username">{{ usuario.login }}</p>
            <p class="description">{{ usuario.bio }}</p>
            <ul>
                <li>
                    <p class="info">Repos</p>
                    <p class="number">{{ usuario.public_repos }}</p>
                </li>
                <li>
                    <p class="info">Followers</p>
                    <p class="number">{{ usuario.followers }}</p>
                </li>
                <li>
                    <p class="info">Following</p>
                    <p class="number">{{ usuario.following }}</p>
                </li>
            </ul>
            <div class="moreInfos">
                <div>
                    <img src="../assets/images/location.svg" alt="">
                    <p>{{ usuario.location }}</p>
                </div>
                <div>
                    <img src="../assets/images/twiter.svg" alt="">
                    <p>{{ twitter_username }}</p>
                </div>
                <div>
                    <img src="../assets/images/copy.svg" alt="">
                    <p>{{ usuario.html_url }}</p>
                </div>
                <div>
                    <img src="../assets/images/companye.svg" alt="">
                    <p>{{ usuario.company }}</p>
                </div>
            </div>
        </div>
    </div>
</template>

<style>
aside{
    img{
        width: 117px;
        height: 117px; 
        border-radius: 100%;
    }
}

.card{
    display: flex;
    gap: 38px;
    padding: 48px;
    border-radius: 15px;
    box-shadow: 0px 8px 20px rgba(0, 0, 0, 0.1);
    transition: all ease 0.7s;

    .header{
        display: flex;
        align-items: center;
        justify-content: space-between;

        h2{
            font-size: 26px;
            font-weight: bold;
        }

        p{
            font-size: 15px;
            font-weight: 400;
        }
    }

    .username{
        font-size: 16px;
        font-weight: 400;
        margin: 2px 0 20px;
        color: #0079FF;
    }

    .description{
        font-size: 15px;
        font-weight: 400;
        line-height: 25px;
        margin-bottom: 32px;
        color: #4B6A9B;
    }

    ul{
        display: flex;
        justify-content: space-between;
        padding: 15px 32px;
        margin-bottom: 38px;
        border-radius: 10px;

        li{
            display: flex;
            flex-direction: column;
            justify-content: center;
            
            .info{
                font-size: 13px;
                font-weight: 400;
                color: #4B6A9B;
            }

            .number{
                font-size: 22px;
                font-weight: bold;
            }
        }
    }

    .moreInfos{
        display: grid;
        grid-template-columns: 1fr 1fr;
        column-gap: 32px;
        row-gap: 15px;

        div{
            display: flex;
            align-items: center;
            gap: 20px;
        }
    }
}

.dark-card{
    background-color: #1E2A47;
    color: #fff;

    .description{
        color: #fff;
    }

    ul{
        background-color: #141D2F;
    }
}
</style>