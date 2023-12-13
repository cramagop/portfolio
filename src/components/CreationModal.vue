<script setup>
    defineProps ({
      modalConfig : Object
    });

    const emit = defineEmits(["closeClicked"]);

    function containLink (item) {
      console.log(item);
      /*if (Reflect.has(item, "islink")) {
        return item.Islink
      } else {
        return false
      }*/
    }

    function onClickClose() {
        emit("closeClicked")
    };
</script>

<template>
    <div @click="onClickClose()" :style="{ display: modalConfig.display }" class="modal">
      <ul>
        <template v-for="(item, key) in modalConfig.content">
          <li v-if="item.hasOwnProperty('isLink')">{{ key }} : <a :href="item.link" target="_blank">{{ item.link }}</a></li>
          <li v-else>{{ key }} : {{ item }}</li>
        </template>
      </ul>
      <!--<div class="modal-content col-flex-wrap-center">
          <h2>{{ modalConfig.content.title }}</h2>
          <div class="row-flex-wrap-center line-content">
            <span class="start">Technologie: </span>
            <span class="end">{{ modalConfig.content.techno }}</span>
          </div>
          <div class="row-flex-wrap-center line-content">
            <span class="start">Date de création: </span>
            <span class="end">{{ modalConfig.content.creationDate }}</span>
          </div>
          <div class="row-flex-wrap-center line-content">
            <span class="start">Lien: </span>
            <a :href="modalConfig.content.creationLink" target="_blank" class="end">Voir la création</a>
          </div>
          <div class="row-flex-wrap-center line-content">
            <span class="start">Git: </span>
            <a :href="modalConfig.content.gitLink" target="_blank" class="end">Aller sur le repo GIT</a>
          </div>
          <button title="Fermer" class="close" @click="onClickClose()">Fermer</button>
      </div>-->
    </div>
</template>

<style scoped>
  h2 {
    margin-left: auto;
    margin-right: auto;
    margin-top: 0.5rem;
    margin-bottom: 1rem;
  }

  button {
    margin-top: 1rem;
    margin-bottom: 1rem;
  }

  p {
    margin: 0rem 0.2rem 0rem 0rem;
  }

  .start {
    font-weight: bold;
    display: flex;
    justify-content: start;
  }
  .end {
    display: flex;
    margin-left: 0.1rem;
  }
  

  .line-content {
    width: 50%;
  }
.modal {
  position: fixed; /* Stay in place */
  padding-top: 5%; /* Location of the box */
  left: 0;
  top: 0;
  width: 100%; /* Full width */
  height: 100%; /* Full height */
  overflow: auto; /* Enable scroll if needed */
  background-color: rgb(0,0,0); /* Fallback color */
  background-color: rgba(0,0,0,0.4); /* Black w/ opacity */
}

/* Modal Content */
.modal-content {
  align-items: center;
  margin: auto;
  padding-left: 1rem;
  padding-right: 1rem;
  width: 30%;
  background-color: #fefefe;
  border: solid 1px black;
  border-radius: 15% 5%;
}

/* The Close Button */
.close {
  justify-self: flex-end;
  color: black;
}

.close:hover, .close:focus {
  color: blue;
  cursor: pointer;
}
</style>