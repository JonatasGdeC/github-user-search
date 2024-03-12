<script>
export default {
    props: {
        usuario: Object
    },
    methods:{
        formatarData(dataString) {
            const meses = ['jan', 'feb', 'mar', 'apr', 'may', 'jun', 'jul', 'aug', 'sep', 'oct', 'nov', 'dec'];
            const data = new Date(dataString);
            const dia = data.getDate();
            const mes = meses[data.getMonth()];
            const ano = data.getFullYear();
            return `Joined ${dia} ${mes} ${ano}`;
        },

        copiarLink(link){   
            let inputElement = document.createElement("input");
            inputElement.value = link;
            document.body.appendChild(inputElement);
            inputElement.select();
            document.execCommand("copy");
            document.body.removeChild(inputElement);
            
            alert("Link copiado para a área de transferência!");
        }
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
                <img :src='usuario.avatar_url' alt="">
                <div class="infos_user">
                    <div>
                        <h2>{{ usuario.name }}</h2>
                        <p class="user_data_desktop">{{formatarData(usuario.created_at)}}</p>
                    </div>
                    <p class="username">{{ usuario.login }}</p>
                    <p class="user_data_tablet">{{formatarData(usuario.created_at)}}</p>
                </div>
            </div>
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
                    <p>{{ usuario.location ? usuario.location : 'Not Available' }}</p>
                </div>
                <div>
                    <img src="../assets/images/twiter.svg" alt="">
                    <p>{{ twitter_username ? twitter_username : 'Not Available' }}</p>
                </div>
                <div>
                    <img src="../assets/images/copy.svg" alt="Copiar link" @click="copiarLink(usuario.html_url)" style="cursor: pointer;">
                    <a :href='usuario.html_url' target="_blank">https://github.blog</a>
                </div>
                <div>
                    <img src="../assets/images/companye.svg" alt="">
                    <p>{{ usuario.company ? usuario.company : 'Not Available' }}</p>
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

    @media(max-width: 1024px){
        display: none;
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

        @media(max-width: 768px){
            h2{
                font-size: 16px;
            }

            p{
                font-size: 13px;
            }
        }

        .infos_user{
            display: flex;
            flex-direction: column;
            margin-bottom: 20px;
            width: 100%;

            div{
                display: flex;
                align-items: center;
                justify-content: space-between;

                @media (max-width: 1024px) {
                    .user_data_desktop{
                        display: none;
                    }
                }
            }

            @media (min-width: 1024px) {
                .user_data_tablet{
                    display: none;
                }
            }
        }

        img{
            width: 117px;
            height: 117px; 
            border-radius: 100%;
            margin: 0 40px 24px 0;
            
            @media(min-width: 1024px){
                display: none;
            }

            @media(max-width: 768px){
                width: 70px;
                height: 70px;
            }
        }
    }

    .username{
        font-size: 16px;
        font-weight: 400;
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

            a{
                color: #4B6A9B;
                &:hover{
                    text-decoration: underline;
                }
            }
        }
    }

    @media(max-width: 768px){
        padding: 32px 24px;
        .username{
            font-size: 13px;
        }

        .description{
            font-size: 13px;
        }

        ul{
            padding: 18px 16px;
            margin-bottom: 24px;

            li{
                text-align: center;
                .info{
                    font-size: 11px;
                }

                .number{
                    font-size: 16px;
                }
            }
        }

        .moreInfos{
            display: flex;
            flex-direction: column;
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

    .moreInfos{
        div{
            a{
                color: #fff;
            }
        }
    }
}
</style>