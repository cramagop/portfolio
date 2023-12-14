<script setup>
    import { ref } from 'vue';
    import creationModal from '../components/creationModal.vue';
    import CreationArticle from '../components/CreationArticle.vue';
    import modalAllConfig from '../assets/content/modalAllConfig'
    import creationArticleContent from '../assets/content/creationArticleContent';

    const modalConfig = ref({
        display: "none",
        content: {
            title: "",
            creationDate: "",
            fileLink: "",
            gitLink: ""}
    });

    const articleContent = ref(creationArticleContent);

    function onModalClickClose() {
        modalConfig.value.display = 'none';
    };

    function onCreationClick(creationName) {
        modalConfig.value = modalAllConfig[creationName];
        modalConfig.value.display = 'block';
    };
</script>

<template>
    <header class="col-flex-wrap-center">
        <figure class="photo-profile">
        <a href="/#main">
            <img class="photo-profile__img"
                src="/pictures/photo_profile_mpo.jpg"
                title="Photo profile Marc POGAM"
                alt="La photo de Marc POGAM">
        </a>
        </figure>
        <nav class="row-flex-wrap-center">
            <a id="prez_link" href="#prez" class="menu-item-link">Présentation</a>
            <a id="creation_link" href="#creation" class="menu-item-link">Création</a>
            <a id="contact_link" href="#contact" class="menu-item-link">Contact</a>
        </nav>
    </header>
    <main>
        <creationModal @close-clicked="onModalClickClose" :modal-config=modalConfig />
        <section class="text-center col-flex-wrap-center">
            <h1 class="presentation-titre">Marc Pogam</h1>
            <p class="presentation-text">
                Passionné par l'informatique en général et plus particuliairement le développement, 
                je vous présente mon portfolio rassemblant quelques unes de mes réalisations.
            </p>
        </section>
        <section class="text-center col-flex-wrap-center">
            <h2>Mes créations</h2>
            <div class="row-flex-wrap-center space-around">
                <CreationArticle v-for="article in articleContent" 
                    :key="article.name" 
                    :article-content="article"
                    @creation-clicked="onCreationClick" />
            </div>
        </section>
        <section>
            <h2>Contactez moi</h2>
        </section>
    </main>
    <footer class="col-flex-wrap-center">
        <div class="row-flex-wrap-center footer__icons">
            <figure class="footer__icon">
                <a href="https://www.linkedin.com/in/marc-pogam-03b046168" target="_blank">
                <img src="/icons/linkedin.png"
                    title="Vers mon linkedin"
                    alt="Lien vers le linkedin de Marc POGAM">
                </a>
            </figure>
            <figure class="footer__icon">
                <a href="https://github.com/cramagop/" target="_blank">
                <img src="/icons/github.png"
                    title="Vers mon github"
                    alt="Lien vers le GitHub de Marc POGAM">
                </a>
            </figure>
        </div>
        <p><small>Dernière mise à jour le <time datetime="2023-11-29">29/11/2023</time></small></p>
    </footer>
</template>

<style scoped>
    nav {
            width: 50%;
            justify-content: space-around;
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

    .space-around {
        width: 90%;
        justify-content: space-between;
    }
    .presentation-titre {
        margin: 1rem;
        font-size: 3rem;
    }

    .presentation-text {
        width: 60%;
        margin-top: 0px;
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