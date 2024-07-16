<template>
    <div class="explore flex-cloumn">
        <h1>Explore our menu</h1>
        <p>
            Choose from a diverse menu featuring a delectable array of dishes.
            Our mission is to satisfy your cravings and elevate your dining
            experience, one delicious meal at a time.
        </p>
        <div class="categories">
            <div
                class="category flex-cloumn"
                v-for="category in categories"
                :key="category.id"
                :class="category.name"
                @click="click(category.id)"
            >
                <div class="thumbnail"></div>
                <span>{{ category.name }}</span>
            </div>
        </div>
        <span class="line"></span>
        <h1>top dishes near you</h1>
        <div class="dishes">
            <div
                v-for="dish in dishes"
                :key="dish.id"
                class="dish"
                :class="dish.img"
            >
                <div class="image">
                    <span></span>
                    <div class="amount">
                        <svg
                            v-if="showCount & (dish.amount != 0)"
                            xmlns="http://www.w3.org/2000/svg"
                            viewBox="0 0 512 512"
                            @click="dish.amount--"
                        >
                            <!--!Font Awesome Free 6.5.2 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free Copyright 2024 Fonticons, Inc.-->
                            <path
                                fill="#ff4c24"
                                d="M256 512A256 256 0 1 0 256 0a256 256 0 1 0 0 512zM184 232H328c13.3 0 24 10.7 24 24s-10.7 24-24 24H184c-13.3 0-24-10.7-24-24s10.7-24 24-24z"
                            />
                        </svg>
                        <p v-if="showCount & (dish.amount != 0)">
                            {{ dish.amount }}
                        </p>
                        <svg
                            xmlns="http://www.w3.org/2000/svg"
                            viewBox="0 0 512 512"
                            @click="
                                showfunc() &
                                    dish.amount++ &
                                    cart.push([
                                        dish.name,
                                        dish.price,
                                        dish.amount,
                                        dish.price * dish.amount,
                                    ]) &
                                    console.log(cart)
                            "
                        >
                            <!--!Font Awesome Free 6.5.2 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free Copyright 2024 Fonticons, Inc.-->
                            <path
                                fill="#81df91"
                                d="M256 512A256 256 0 1 0 256 0a256 256 0 1 0 0 512zM232 344V280H168c-13.3 0-24-10.7-24-24s10.7-24 24-24h64V168c0-13.3 10.7-24 24-24s24 10.7 24 24v64h64c13.3 0 24 10.7 24 24s-10.7 24-24 24H280v64c0 13.3-10.7 24-24 24s-24-10.7-24-24z"
                            />
                        </svg>
                    </div>
                </div>
                <div class="details flex-cloumn">
                    <div class="inform">
                        <h3>{{ dish.name }}</h3>
                        <div class="rate">
                            <svg
                                xmlns="http://www.w3.org/2000/svg"
                                viewBox="0 0 576 512"
                            >
                                <path
                                    fill="#ff4c24"
                                    d="M316.9 18C311.6 7 300.4 0 288.1 0s-23.4 7-28.8 18L195 150.3 51.4 171.5c-12 1.8-22 10.2-25.7 21.7s-.7 24.2 7.9 32.7L137.8 329 113.2 474.7c-2 12 3 24.2 12.9 31.3s23 8 33.8 2.3l128.3-68.5 128.3 68.5c10.8 5.7 23.9 4.9 33.8-2.3s14.9-19.3 12.9-31.3L438.5 329 542.7 225.9c8.6-8.5 11.7-21.2 7.9-32.7s-13.7-19.9-25.7-21.7L381.2 150.3 316.9 18z"
                                />
                            </svg>
                            <svg
                                xmlns="http://www.w3.org/2000/svg"
                                viewBox="0 0 576 512"
                            >
                                <path
                                    fill="#ff4c24"
                                    d="M316.9 18C311.6 7 300.4 0 288.1 0s-23.4 7-28.8 18L195 150.3 51.4 171.5c-12 1.8-22 10.2-25.7 21.7s-.7 24.2 7.9 32.7L137.8 329 113.2 474.7c-2 12 3 24.2 12.9 31.3s23 8 33.8 2.3l128.3-68.5 128.3 68.5c10.8 5.7 23.9 4.9 33.8-2.3s14.9-19.3 12.9-31.3L438.5 329 542.7 225.9c8.6-8.5 11.7-21.2 7.9-32.7s-13.7-19.9-25.7-21.7L381.2 150.3 316.9 18z"
                                />
                            </svg>
                            <svg
                                xmlns="http://www.w3.org/2000/svg"
                                viewBox="0 0 576 512"
                            >
                                <path
                                    fill="#ff4c24"
                                    d="M316.9 18C311.6 7 300.4 0 288.1 0s-23.4 7-28.8 18L195 150.3 51.4 171.5c-12 1.8-22 10.2-25.7 21.7s-.7 24.2 7.9 32.7L137.8 329 113.2 474.7c-2 12 3 24.2 12.9 31.3s23 8 33.8 2.3l128.3-68.5 128.3 68.5c10.8 5.7 23.9 4.9 33.8-2.3s14.9-19.3 12.9-31.3L438.5 329 542.7 225.9c8.6-8.5 11.7-21.2 7.9-32.7s-13.7-19.9-25.7-21.7L381.2 150.3 316.9 18z"
                                />
                            </svg>
                            <svg
                                xmlns="http://www.w3.org/2000/svg"
                                viewBox="0 0 576 512"
                            >
                                <path
                                    fill="#ff4c24"
                                    d="M316.9 18C311.6 7 300.4 0 288.1 0s-23.4 7-28.8 18L195 150.3 51.4 171.5c-12 1.8-22 10.2-25.7 21.7s-.7 24.2 7.9 32.7L137.8 329 113.2 474.7c-2 12 3 24.2 12.9 31.3s23 8 33.8 2.3l128.3-68.5 128.3 68.5c10.8 5.7 23.9 4.9 33.8-2.3s14.9-19.3 12.9-31.3L438.5 329 542.7 225.9c8.6-8.5 11.7-21.2 7.9-32.7s-13.7-19.9-25.7-21.7L381.2 150.3 316.9 18z"
                                />
                            </svg>
                            <svg
                                xmlns="http://www.w3.org/2000/svg"
                                viewBox="0 0 576 512"
                            >
                                <path
                                    fill="#ff4c24"
                                    d="M287.9 0c9.2 0 17.6 5.2 21.6 13.5l68.6 141.3 153.2 22.6c9 1.3 16.5 7.6 19.3 16.3s.5 18.1-5.9 24.5L433.6 328.4l26.2 155.6c1.5 9-2.2 18.1-9.7 23.5s-17.3 6-25.3 1.7l-137-73.2L151 509.1c-8.1 4.3-17.9 3.7-25.3-1.7s-11.2-14.5-9.7-23.5l26.2-155.6L31.1 218.2c-6.5-6.4-8.7-15.9-5.9-24.5s10.3-14.9 19.3-16.3l153.2-22.6L266.3 13.5C270.4 5.2 278.7 0 287.9 0zm0 79L235.4 187.2c-3.5 7.1-10.2 12.1-18.1 13.3L99 217.9 184.9 303c5.5 5.5 8.1 13.3 6.8 21L171.4 443.7l105.2-56.2c7.1-3.8 15.6-3.8 22.6 0l105.2 56.2L384.2 324.1c-1.3-7.7 1.2-15.5 6.8-21l85.9-85.1L358.6 200.5c-7.8-1.2-14.6-6.1-18.1-13.3L287.9 79z"
                                />
                            </svg>
                        </div>
                    </div>
                    <p>{{ dish.detail }}</p>
                    <span class="price"> {{ dish.price }} $</span>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import { ref } from "vue";

export default {
    name: "exploreComponent",

    setup() {
        const categories = ref([]);
        const dishes = ref([]);
        const num = ref(1);
        const showCount = ref(false);
        const cart = ref([]);
        const load = async () => {
            try {
                const data = await fetch("http://localhost:3000/categories");
                categories.value = await data.json();
                dishes.value =
                    categories.value[Math.floor(Math.random() * 8)]["dishes"];
            } catch (error) {
                console.log(error.message);
            }
        };
        load();
        const click = (id) => {
            num.value = id;
            dishes.value = categories.value[num.value - 1]["dishes"];
        };
        const showfunc = () => {
            showCount.value = true;
        };
        return { categories, dishes, click, showCount, showfunc, cart };
    },
};
</script>

<style scoped>
.explore {
    margin-top: 20px;
    gap: 15px;
    text-align: left;
}
.explore h1 {
    color: #211c1cf7;
}
.explore > p {
    max-width: 70%;
    font-size: 17px;
    font-weight: 600;
    color: #211c1cab;
}
.explore .categories {
    display: flex;
    justify-content: space-between;
    width: 100%;

    margin-top: 10px;
}
.explore .categories .category {
    align-items: center;
    text-align: center;
    gap: 5px;
    color: #211c1cab;
    font-weight: 600;
}
.explore .categories .category .thumbnail {
    height: 100px;
    width: 100px;
    border-radius: 50%;
    border: 2px SOLID transparent;
    background-origin: border-box;
    background-size: cover;
    transition: border-color var(--main-transition);
}
.thumbnail:hover {
    border-color: var(--effect-color) !important;
}
.explore .categories .category.salad .thumbnail {
    background-image: url("/src/assets/frontend_assets/menu_1.png");
    background-origin: border-box;
    background-size: contain;
}
.explore .categories .category.Rolls .thumbnail {
    background-image: url("/src/assets/frontend_assets/menu_2.png");
}
.explore .categories .category.Deserts .thumbnail {
    background-image: url("/src/assets/frontend_assets/menu_3.png");
}
.explore .categories .category.Sandwish .thumbnail {
    background-image: url("/src/assets/frontend_assets/menu_4.png");
}
.explore .categories .category.Cake .thumbnail {
    background-image: url("/src/assets/frontend_assets/menu_5.png");
}
.explore .categories .category.Pure .thumbnail {
    background-image: url("/src/assets/frontend_assets/menu_6.png");
}
.explore .categories .category.Pasta .thumbnail {
    background-image: url("/src/assets/frontend_assets/menu_7.png");
}
.explore .categories .category.Noodles .thumbnail {
    background-image: url("/src/assets/frontend_assets/menu_8.png");
}
.line {
    background-color: #211c1c2e;
    width: 100%;
    height: 2px;
    margin-top: 40px;
}
.dishes {
    margin-top: 10px;
    width: 100%;
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 40px 15px;
}

.dishes .dish {
    height: 370px;
    border-radius: 10px;
    box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
    overflow: hidden;
    transition: transform var(--main-transition);
}
.dishes .dish:hover {
    transform: scale(1.05);
}
.dishes .dish .image {
    overflow: hidden;
    position: relative;
}
.dishes .dish .image span {
    display: block;
    background-image: url("/src/assets/frontend_assets/food_22.png");
    height: 200px;
    background-size: cover;
    background-position: bottom;
}
.dishes .dish.firstSalad .image span {
    background-image: url("/src/assets/frontend_assets/food_1.png");
}
.dishes .dish.secondSalad .image span {
    background-image: url("/src/assets/frontend_assets/food_21.png");
}
.dishes .dish.thirdSalad .image span {
    background-image: url("/src/assets/frontend_assets/food_2.png");
}
.dishes .dish.fourthSalad .image span {
    background-image: url("/src/assets/frontend_assets/food_24.png");
}
.dishes .dish.fifthSalad .image span {
    background-image: url("/src/assets/frontend_assets/food_22.png");
}
.dishes .dish.firstroll .image span {
    background-image: url("/src/assets/frontend_assets/food_15.png");
}
.dishes .dish.secondroll .image span {
    background-image: url("/src/assets/frontend_assets/food_16.png");
}
.dishes .dish.thirdroll .image span {
    background-image: url("/src/assets/frontend_assets/food_8.png");
}
.dishes .dish.fourthroll .image span {
    background-image: url("/src/assets/frontend_assets/food_6.png");
}
.dishes .dish.fifthroll .image span {
    background-image: url("/src/assets/frontend_assets/food_7.png");
}
.dishes .dish.firstDesert .image span {
    background-image: url("/src/assets/frontend_assets/food_11.png");
}
.dishes .dish.secondDesert .image span {
    background-image: url("/src/assets/frontend_assets/food_17.png");
}
.dishes .dish.thirdDesert .image span {
    background-image: url("/src/assets/frontend_assets/food_18.png");
}
.dishes .dish.fourthDesert .image span {
    background-image: url("/src/assets/frontend_assets/food_19.png");
}

.dishes .dish.fifthDesert .image span {
    background-image: url("/src/assets/frontend_assets/food_20.png");
}
.dish .amount {
    position: absolute;
    right: 5%;
    top: 80%;
    display: flex;
    justify-content: space-between;
    background-color: #fff;
    padding: 7px;
    border-radius: 20px;
    gap: 15px;
}
.dishes .dish .details {
    padding: 15px;
    gap: 5px;
}

.dishes .dish .inform {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
}

.dishes .dish .inform h3 {
    color: #211c1cf7;
}
.dishes .dish .inform .rate {
    min-width: 30%;
}
.dishes .dish .inform .rate svg {
    width: 15px;
}
.dishes .dish .details p {
    width: 100% !important;
    font-size: 14px;
    font-weight: 600;
    color: #211c1c91;
}
.dishes .dish .details .price {
    color: var(--effect-color);
    font-size: 20px;
    font-weight: 700;
}
</style>
