<script setup>
    import { RouterView } from 'vue-router'
</script>

<template>
    <header class="col-flex-wrap-center">
        <figure class="photo-profile">
            <a href="/#main">
                <img class="photo-profile__img"
                    src="./assets/pictures/photo_profile_mpo.jpg"
                    title="Photo profile Marc POGAM"
                    alt="La photo de Marc POGAM">
            </a>
        </figure>
        <nav class="row-flex-wrap-center">
            <div class="menu-item">
                <a id="prez_link" href="#prez" class="menu-item-link">Présentation</a>
            </div>
            <div class="menu-item">
                <a id="creation_link" href="#creation" class="menu-item-link">Création</a>
            </div>
            <div class="menu-item">
                <a id="contact_link" href="/" class="menu-item-link">Contact</a>
            </div>
        </nav>
    </header>

    <main id="main">
        <RouterView />
    </main>

    <footer class="col-flex-wrap-center">
        <div class="row-flex-wrap-center footer__icons">
            <figure class="footer__icon">
                <a href="https://www.linkedin.com/in/marc-pogam-03b046168" target="_blank">
                <img src="./assets/icons/linkedin.png"
                    title="Vers mon linkedin"
                    alt="Lien vers le linkedin de Marc POGAM">
                </a>
            </figure>
            <figure class="footer__icon">
                <a href="https://github.com/cramagop/" target="_blank">
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
    nav {
        width: 50%;
        justify-content: space-around;
    }
    .menu-item {
        display: flex;
        flex: 33%;
        justify-content: center;
        border-top: solid 1px black;
        border-left: solid 1px black;
        border-right: solid 1px black;
    }

    .menu-item-link {
        text-decoration: none;
        font-size: 1.5rem;
    }
    .photo-profile {
        width: 150px;
        height: 150px;
        margin-top: 30px;
    }

    .photo-profile__img {
        border-radius: 50%;
        box-shadow: 0 0 15px black;
    }

    .footer__icons {
      margin-top: 10px;
   }

    .footer__icon {
        width: 50px;
        height: 50px;
        margin: 10px;
    }
    .footer__icon img:hover {
        opacity: 0.5;
    }
</style>