<script setup>
import { RouterView } from 'vue-router'
</script>

<template>
    <header class="flex-wrap-col-center">
        <figure class="photo-profile">
            <a href="" target="_blank">
                <img class="photo-profile__img"
                    src="./assets/pictures/photo_profile_mpo.jpg"
                    title="Photo profile Marc POGAM"
                    alt="La photo de Marc POGAM">
            </a>
        </figure>
    </header>

    <RouterView />

    <footer>
        <div class="footer__icons">
            <figure class="footer__icon">
                <a href="https://www.linkedin.com/in/marc-pogam-03b046168" target="_blank">
                <img src="./assets/icons/linkedin.png"
                    title="Vers mon linkedin"
                    alt="Lien vers le linkedin de Marc POGAM">
                </a>
            </figure>
            <figure class="footer__icon">
                <a href="https://www.linkedin.com/in/marc-pogam-03b046168" target="_blank">
                <img src="./assets/icons/github.png"
                    title="Vers mon github"
                    alt="Lien vers le GitHub de Marc POGAM">
                </a>
            </figure>
        </div>
        <p>Dernière mise à jour le <time datetime="2023-11-29">29/11/2023</time></p>
    </footer>
</template>

<style scoped>
    .photo-profile {
        width: 150px;
        height: 150px;
        margin-top: 30px;
    }

    .photo-profile__img {
        width: 100%;
        height: 100%;
        border-radius: 50%;
        box-shadow: 0 0 15px #dbc2a4;
    }

    .footer__icons {
      display: flex;
      flex-direction: row;
      flex-wrap: wrap;
      justify-content: center;
      margin-top: 10px;
   }
    .footer__icon {
        width: 50px;
        height: 50px;
        margin: 10px;
    }
    .footer__icon img {
    width: 100%;
    height: 100%;
    }

    .footer__icon img:hover {
        opacity: 0.5;
    }
</style>