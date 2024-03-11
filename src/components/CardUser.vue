<script>
// import './CardUser.scss'
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

<style>
    .card{
    display: flex;
    gap: 38px;
    padding: 48px;

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
</style>