<script setup>
    import { ref } from 'vue';
    import creationModal from './creationModal.vue';
    import CreationArticle from './CreationArticle.vue';
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

    const emit = defineEmits(["mouseOver", "mouseOut"]);

    function onMouseOver(parentElementIDtoImpact) {
        emit("mouseOver", parentElementIDtoImpact);
    };

    function onMouseOut(parentElementIDtoImpact) {
        emit("mouseOut", parentElementIDtoImpact);
    };

    function onModalClickClose() {
        modalConfig.value.display = 'none';
    };

    function onCreationClick(creationName) {
        modalConfig.value = modalAllConfig[creationName];
        modalConfig.value.display = 'block';
    };
</script>

<template>
    <creationModal @close-clicked="onModalClickClose" :modal-config=modalConfig />
    <section id="prez" 
            @mouseover="onMouseOver('prez_link')"
            @mouseout="onMouseOut('prez_link')"
            class="text-center col-flex-wrap-center">
            <h1 class="presentation-titre">Marc Pogam</h1>
            <p class="presentation-text">
                Passionné par l'informatique en général et plus particuliairement le développement, 
                je vous présente mon portfolio rassemblant quelques unes de mes réalisations.
            </p>
    </section>
    <section id="creation"
            @mouseover="onMouseOver('creation_link')"
            @mouseout="onMouseOut('creation_link')"
            class="text-center col-flex-wrap-center">
            <h2>Mes créations</h2>
            <div class="row-flex-wrap-center space-around">
                <CreationArticle v-for="article in articleContent" 
                    :key="article.name" 
                    :article-content="article"
                    @creation-clicked="onCreationClick" />
            </div>
    </section>
    <section id="contact"
            @mouseover="onMouseOver('contact_link')"
            @mouseout="onMouseOut('contact_link')">
            <h2>Contactez moi</h2>
    </section>
</template>

<style scoped>
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
</style>