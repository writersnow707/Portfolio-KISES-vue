<script setup>
    import { introText } from '../constants';
</script>

<template>
     <section id="intro">
            <div class="intro_inner">
                <h2 class="intro_title">
                    KISES 소개<em></em>
                </h2>
                <div class="intro_desc">
                    <div v-for="(intro, key) in introText" :key="key">
                        <span>{{key+1}}.</span>
                        <img v-bind:src="intro.img" />
                        <h3>{{ intro.title }}</h3>
                        <p>{{ intro.desc }}</p>
                     </div>                  
                </div>                
            </div>
        </section>
</template>

<style lang="scss">
    .intro_inner{
    padding: 16px;
    display: flex; // 소개글 위치 조정?
    justify-content: space-between;

    @media(max-width: 800px){        
            flex-direction: column;
        }

    .intro_title{
        position: sticky; // 제목 위치
        top: 80px;
        left: 0;
        width: 48%;
        height: 5vw;
        font-size: 4vw;
        font-weight: 900;
        line-height: 1.5;
        font-family: var(--mainKor-font);
        text-transform: uppercase;
        color: var(--black100);
        border-bottom: 0.4vw solid var(--black100);   

        @media(max-width: 800px){
            width: 100%;
            margin-bottom: 10vw;
            font-size: 30px;
            height: auto;
            top: 68px;
            background-color: var(--mainBg-color);
        }

        em{
            font-size: 1.25rem;
            font-weight: 400;
            line-height: 2;
        }
    }
    .intro_desc{
        width: 50%;

        @media(max-width: 800px){
            width: 100%;
        }

        span{
            font-size: 5vw;
            line-height: 1.3;
            font-weight: 900;
            font-family: var(--mainNum-font);

            @media(max-width: 800px){
                font-size: 20vw;

            }
        }
        h3{
            font-size: 1.5rem;
            text-decoration: underline;
            text-underline-position: under;
            margin-bottom: 1vw;
        }
        p{
            margin-bottom: 3vh;
            font-size: 1.1rem;
        }
    }
}
</style>