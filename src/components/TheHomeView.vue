<template>
    <section class="text-center col-flex-wrap-center">
        <h1 class="presentation-titre">Marc Pogam</h1>
        <p class="presentation-text">
            Passionné par l'informatique en général et plus particuliairement le développement, 
            je vous présente mon portfolio rassemblant quelques unes de mes réalisations.
        </p>
    </section>
    <section class="text-center row-flex-wrap-center">
        <article>
            <figure class="photo-profile">
                <a href="/">
                    <img class="photo-profile__img"
                        src="../assets//pictures/photo_profile_mpo.jpg"
                        title="Photo profile Marc POGAM"
                        alt="La photo de Marc POGAM">
                </a>
            </figure>
            <h2>Mon CV</h2>
        </article>
        <article>
            <figure class="photo-profile">
                <a href="/">
                    <img class="photo-profile__img"
                        src="../assets//pictures/photo_profile_mpo.jpg"
                        title="Photo profile Marc POGAM"
                        alt="La photo de Marc POGAM">
                </a>
            </figure>
            <h2>Dynamiser un formulaire</h2>
        </article>
        <article>
            <figure class="photo-profile">
                <a href="/">
                    <img class="photo-profile__img"
                        src="../assets//pictures/photo_profile_mpo.jpg"
                        title="Photo profile Marc POGAM"
                        alt="La photo de Marc POGAM">
                </a>
            </figure>
            <h2>Un cahier des charges</h2>
        </article>
    </section>
    <section>
        <form action="#" method="POST">
          <div class="row-flex-wrap-center">
            <label for="first-name">Prénom</label>
            <div>
              <input type="text" name="first-name" id="first-name" autocomplete="given-name">
            </div>
          </div>
          <div>
            <label for="last-name">Nom</label>
            <div class="mt-1">
              <input type="text" name="last-name" id="last-name" autocomplete="family-name">
            </div>
          </div>
          <div>
            <div>
              <label for="message">Commentaire</label>
              <span id="message-max">Max. 500 caractères</span>
            </div>
            <div class="mt-1">
              <textarea id="message" name="message" rows="4" maxlength="500"></textarea>
            </div>
          </div>
          <div>
            <button type="submit">
              Envoyer
            </button>
          </div>
        </form>
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

    .photo-profile {
        width: 150px;
        height: 150px;
        margin-top: 30px;
    }

    .photo-profile__img {
        /*border-radius: 50%;*/
        box-shadow: 0 0 15px black;
    }
</style>