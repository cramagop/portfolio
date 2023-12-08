<script setup>
    defineProps ({
        articleContent: Object
    });

    const emit = defineEmits(["creationClicked"]);

    function getIgSrcLocalPath (imgSrc) {
        return '../assets/pictures/' + imgSrc;
    }
    
    function onCreationClick(creationName) {
        emit("creationClicked", creationName);
    };

</script>


<template>
    <article @click="onCreationClick(articleContent.name)" class="col-flex-wrap-center">
        <figure class="picture-creation">
            <img class="picture-creation__img"
                :src="getIgSrcLocalPath(articleContent.imgSrc)"
                :title="articleContent.imgTitle"
                :alt="articleContent.imgAlt">
        </figure>
        <h2>{{articleContent.title}}</h2>
    </article>
    <!--
    <article @click="onCreationClick(articleContent.name)" class="col-flex-wrap-center">
        <figure class="picture-creation">
            <img class="picture-creation__img"
                :src="`${imgSrc}`"
                title={{articleContent.imgTitle}}
                alt={{articleContent.imgAlt}}>
        </figure>
        <h2>{{articleContent.title}}</h2>
    </article>
    -->
</template>

<style scoped>
    .picture-creation {
        width: 150px;
        height: 150px;
        margin-top: 30px;
    }

    .picture-creation__img {
        box-shadow: 0 0 15px black;
    }
</style>