<script setup>
    import { ref } from 'vue';
    import creationModal from './creationModal.vue';
    import modalAllConfig from '../assets/content/modalAllConfig'

    const modalConfig = ref({
        display: "none",
        content: {
            title: "",
            creationDate: "",
            fileLink: "",
            gitLink: ""}
    });

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
    }

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
            class="text-center row-flex-wrap-center">
        <article @click="onCreationClick('cv')">
            <figure class="picture-creation">
                <img class="picture-creation__img"
                    src="../assets//pictures/cv.png"
                    title="CV"
                    alt="Icône représentant un CV">
            </figure>
            <h2>Mon CV</h2>
        </article>
        <article @click="onCreationClick('formulaire')">
            <figure class="picture-creation">
                <img class="picture-creation__img"
                    src="../assets//pictures/formulaire.PNG"
                    title="Formulaire"
                    alt="Un formulaire avec des champs vide">
            </figure>
            <h2>Dynamiser un formulaire</h2>
        </article>
        <article @click="onCreationClick('cahierDesCharges')">
            <figure class="picture-creation">
                <img class="picture-creation__img"
                    src="../assets//pictures/La socketterie.png"
                    title="Cahier des charges"
                    alt="Un paire de chaussette titré la socketterie">
            </figure>
            <h2>Un cahier des charges</h2>
        </article>
    </section>
    <section id="contact"
            @mouseover="onMouseOver('contact_link')"
            @mouseout="onMouseOut('contact_link')">

    </section>
</template>

<style scoped>
    
    h2 {
        margin-left: 0.5rem;
        margin-right: 0.5rem;
    }

    article {
        display: flex;
        flex-wrap: wrap;
        flex-direction: column;
        align-items: center;
        margin-bottom: 1rem;
    }

    article:hover {
        box-shadow: 5px 5px 10px black;
    }

    .isDisplay {
        display: block;
    }

    .row-flex-wrap-center {
        display: flex;
        flex-wrap: wrap;
        flex-direction: row;
        justify-content: space-evenly;
        align-content: space-around;
    }

    .presentation-titre {
        margin: 1rem;
        font-size: 3rem;
    }

    .presentation-text {
        width: 60%;
        margin-top: 0px;
    }

    .picture-creation {
        width: 150px;
        height: 150px;
        margin-top: 30px;
    }

    .picture-creation__img {
        box-shadow: 0 0 15px black;
    }
</style>