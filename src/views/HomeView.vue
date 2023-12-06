<script setup>
  import TheHomeView from '../components/TheHomeView.vue'

  /**
   * Choose parent HTMLElement impacted by child HTMLElement event
   * @param {String} childElementID
   * @return {HTMLElement} Parent HTMLElement impacted
  */ 
  function parentElementToImpact(childElementID) {
        switch(childElementID){
            case 'prez':
                return document.getElementById('prez_link');
            case 'creation':
                return document.getElementById('creation_link');
            case 'contact':
                return document.getElementById('contact_link')
        };
    };

    function underline(childElementID) {
        parentElementToImpact(childElementID).style.textDecoration = "underline";
    }

    function unUnderline(childElementID) {
        parentElementToImpact(childElementID).style.textDecoration = "none";
    }

</script>

<template>
  <TheHomeView @mouse-over="underline" @mouse-out="unUnderline"/>
</template>