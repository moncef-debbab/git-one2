<template>
    <div>
        <singupForm v-if="showsingUpForm" @singEvent="cancel" />
        <headerComponent @singEvent="call" />
        <router-view />
    </div>
</template>

<script>
import headerComponent from "../src/components/headerComponents/headerComponent.vue";
import singupForm from "../src/components/signComponents/signupComponent.vue";
export default {
    components: {
        headerComponent,
        singupForm,
    },
    data() {
        return {
            showsingUpForm: false,
        };
    },
    methods: {
        call() {
            this.showsingUpForm = true;
        },
        cancel() {
            this.showsingUpForm = false;
        },
    },
};
</script>
<style>
:root {
    --main-color: #40557e;
    --main-transition: 0.3s ease;
    --effect-color: #ff4c24;
}
* {
    margin: 0;
    box-sizing: border-box;
    padding: 0;
    text-decoration: none;
    text-transform: capitalize;
    list-style: none;
}

#app {
    font-family: "Tajawal", sans-serif;
    font-style: normal;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #40557e;
    padding: 20px 150px 0px;
}
svg {
    width: 20px;
}
.flex-cloumn {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
}
@keyframes fadeIn {
    0% {
        opacity: 0;
    }
    100% {
        opacity: 1;
    }
}
/* Media query for screens smaller than 600px */

@media (max-width: 721px) {
    #app {
        padding: 20px 16px 0px;
    }
    .header ul,
    .categories,
    .definition .details {
        display: none !important;
    }
    .header img {
        width: 40%;
    }
    .header button {
        padding: 2px 16px !important;
    }
    .definition {
        background-size: cover !important;
        padding: 16px 7px !important;
        height: 210px !important ;
    }

    .definition .content {
        width: 100%;
        gap: 25px !important;
    }
    .definition .content .text,
    .explore p {
        max-width: 100% !important;
    }
    .definition .content .slogun {
        font-size: 33px !important;
        gap: 18px !important;
    }
    .definition .content button {
        height: 35px !important;
        padding: 3px 12px !important;
    }
    .mobiles h1 {
        font-size: 25px !important;
    }
    .mobiles .logos {
        flex-direction: column;
    }
    .footer {
        width: calc(100% + 32px) !important;
        margin-left: -16px !important;
        gap: 20px !important;
    }
    .footer .details {
        flex-direction: column !important;
        padding: 0 !important;
        text-align: center !important;

        align-items: center !important;
    }
    .footer .details .definition {
        text-align: center !important;
        height: 100% !important;
        width: 100% !important;
        padding: 0 !important;

        align-items: center !important;
    }
    .footer .details .definition p {
        text-align: center !important;
    }

    .footer .details .definition .img {
        width: 173px !important;
    }
    .footer .company ul {
        flex-direction: row !important;
    }
    .footer .details .touch {
        align-items: center !important;
        width: 100% !important;
    }
}

/* Media query for screens between 601px and 1200px */

@media (min-width: 722px) and (max-width: 1200px) {
    #app {
        padding: 20px 30px 0px;
    }
    /* .header ul, */
    .categories {
        display: none !important;
    }
    .header img {
        width: 20%;
    }
    .header button {
        padding: 2px 16px !important;
    }

    .definition {
        background-size: cover !important;
        padding: 16px 30px !important;
        height: 350px !important ;
    }

    .definition .content {
        width: 100%;
        gap: 25px !important;
    }
    .definition .content .text,
    .explore p {
        max-width: 86% !important;
    }
    .definition .content .slogun {
        font-size: 40px !important;
        gap: 18px !important;
    }
    .definition .content button {
        height: 35px !important;
        padding: 3px 12px !important;
    }
    .mobiles h1 {
        font-size: 35px !important;
    }
    .mobiles .logos {
        flex-direction: row;
    }
    .footer {
        width: calc(100% + 32px) !important;
        margin-left: -16px !important;
        gap: 20px !important;
    }
    .footer .details {
        flex-direction: column !important;
        padding: 0 !important;
        text-align: center !important;

        align-items: center !important;
    }
    .footer .details .definition {
        text-align: center !important;
        height: 100% !important;
        width: 100% !important;
        padding: 0 !important;

        align-items: center !important;
    }
    .footer .details .definition p {
        text-align: center !important;
    }

    .footer .details .definition .img {
        width: 173px !important;
    }
    .footer .company ul {
        flex-direction: row !important;
    }
    .footer .details .touch {
        align-items: center !important;
        width: 100% !important;
    }
}

/* Media query for screens larger than 1200px */

/* @media (min-width: 1201px) {
}  */
</style>
