<template>
    <div class="footer flex-cloumn">
        <div class="details">
            <div class="definition">
                <div class="img" alt="" />
                <p class="text">
                    Choose From A Diverse Menu Featuring A Delectable Array Of
                    Dishes Crafted With The Finest Ingredients And Culinary
                    Expertise. Our Mission Is To Satisfy Your Cravings And
                    Elevate Your Dining Experience, One Delicious Meal At A
                    Time.
                </p>
                <ul>
                    <li>
                        <svg
                            xmlns="http://www.w3.org/2000/svg"
                            viewBox="0 0 512 512"
                        >
                            <!--!Font Awesome Free 6.5.2 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free Copyright 2024 Fonticons, Inc.-->
                            <path
                                d="M512 256C512 114.6 397.4 0 256 0S0 114.6 0 256C0 376 82.7 476.8 194.2 504.5V334.2H141.4V256h52.8V222.3c0-87.1 39.4-127.5 125-127.5c16.2 0 44.2 3.2 55.7 6.4V172c-6-.6-16.5-1-29.6-1c-42 0-58.2 15.9-58.2 57.2V256h83.6l-14.4 78.2H287V510.1C413.8 494.8 512 386.9 512 256h0z"
                            />
                        </svg>
                    </li>
                    <li>
                        <svg
                            xmlns="http://www.w3.org/2000/svg"
                            viewBox="0 0 448 512"
                        >
                            <!--!Font Awesome Free 6.5.2 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free Copyright 2024 Fonticons, Inc.-->
                            <path
                                d="M64 32C28.7 32 0 60.7 0 96V416c0 35.3 28.7 64 64 64H384c35.3 0 64-28.7 64-64V96c0-35.3-28.7-64-64-64H64zm297.1 84L257.3 234.6 379.4 396H283.8L209 298.1 123.3 396H75.8l111-126.9L69.7 116h98l67.7 89.5L313.6 116h47.5zM323.3 367.6L153.4 142.9H125.1L296.9 367.6h26.3z"
                            />
                        </svg>
                    </li>
                    <li>
                        <svg
                            xmlns="http://www.w3.org/2000/svg"
                            viewBox="0 0 448 512"
                        >
                            <!--!Font Awesome Free 6.5.2 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free Copyright 2024 Fonticons, Inc.-->
                            <path
                                d="M416 32H31.9C14.3 32 0 46.5 0 64.3v383.4C0 465.5 14.3 480 31.9 480H416c17.6 0 32-14.5 32-32.3V64.3c0-17.8-14.4-32.3-32-32.3zM135.4 416H69V202.2h66.5V416zm-33.2-243c-21.3 0-38.5-17.3-38.5-38.5S80.9 96 102.2 96c21.2 0 38.5 17.3 38.5 38.5 0 21.3-17.2 38.5-38.5 38.5zm282.1 243h-66.4V312c0-24.8-.5-56.7-34.5-56.7-34.6 0-39.9 27-39.9 54.9V416h-66.4V202.2h63.7v29.2h.9c8.9-16.8 30.6-34.5 62.9-34.5 67.2 0 79.7 44.3 79.7 101.9V416z"
                            />
                        </svg>
                    </li>
                </ul>
            </div>
            <div class="company">
                <h1>company</h1>
                <ul class="flex-cloumn">
                    <li>
                        <router-link :to="{ name: 'home' }">Home</router-link>
                    </li>
                    <li>
                        <router-link :to="{ name: 'Contact' }"
                            >Contact</router-link
                        >
                    </li>
                    <li>
                        <router-link :to="{ name: 'menu' }">menu</router-link>
                    </li>
                    <li>
                        <router-link :to="{ name: 'MobileApp' }"
                            >MobileApp</router-link
                        >
                    </li>
                </ul>
            </div>
            <div class="touch flex-cloumn">
                <h1>get in touch</h1>
                <p>+213657689870</p>
                <p class="email">contact@moncef.dev</p>
            </div>
        </div>
        <div class="copywriting">
            copyright {{ year }}
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512">
                <!--!Font Awesome Free 6.5.2 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free Copyright 2024 Fonticons, Inc.-->
                <path
                    d="M256 512A256 256 0 1 0 256 0a256 256 0 1 0 0 512zM199.4 312.6c31.2 31.2 81.9 31.2 113.1 0c9.4-9.4 24.6-9.4 33.9 0s9.4 24.6 0 33.9c-50 50-131 50-181 0s-50-131 0-181s131-50 181 0c9.4 9.4 9.4 24.6 0 33.9s-24.6 9.4-33.9 0c-31.2-31.2-81.9-31.2-113.1 0s-31.2 81.9 0 113.1z"
                /></svg
            >Tomato.com - All right reversed
        </div>
    </div>
</template>

<script>
export default {
    name: "footerComponent",
    data() {
        return {
            year: new Date().getFullYear(),
        };
    },
};
</script>

<style>
.footer {
    background-color: #26272b;
    display: flex;
    gap: 50px;
    width: calc(100% + 300px);
    margin-left: -150px;
    align-items: center;
    color: whitesmoke;
    padding-bottom: 10px;
    margin-top: 100px;
}
.footer .details {
    margin-top: 100px;
    align-items: baseline;
    gap: 10%;
    padding: 0 50px;
    display: flex;
}
.footer .details .definition {
    display: flex;
    flex-direction: column;
    width: 50%;
    gap: 20px;
}
.footer .details .definition .img {
    background-image: url("/src/assets/frontend_assets/logo.png");
    height: 34px;
    width: 173.45px;
}
.footer .details .definition p {
    width: 90%;
    text-align: left;
}
.footer .details .definition ul {
    display: flex;
    width: 30%;
    justify-content: space-between;
}
.footer .details .definition ul svg {
    width: 30px;
}

.footer .details .company ul {
    gap: 10px;
}
.footer .details .company h1,
.footer .details .touch h1 {
    color: var(--effect-color);
}
.footer .details .company ul a {
    font-size: 20px;
    color: whitesmoke;
}
.footer .details .touch {
    width: 20%;
}
.footer .copywriting {
    text-transform: none;
    display: flex;
    align-items: center;
    gap: 3px;
    font-size: 17px;
}
.footer .copywriting svg {
    width: 15px;
}
</style>
