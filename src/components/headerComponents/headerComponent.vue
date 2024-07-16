<template>
    <div class="header">
        <img src="../../assets/frontend_assets/logo.png" alt="" />
        <ul>
            <router-link to="/">Home</router-link>
            <router-link :to="{ name: 'menu' }">Menu</router-link>
            <router-link :to="{ name: 'MobileApp' }">Mobile App</router-link>
            <router-link :to="{ name: 'Contact' }">Contact Us</router-link>
        </ul>
        <div class="icons">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512">
                <path
                    fill=" #40557e"
                    d="M416 208c0 45.9-14.9 88.3-40 122.7L502.6 457.4c12.5 12.5 12.5 32.8 0 45.3s-32.8 12.5-45.3 0L330.7 376c-34.4 25.2-76.8 40-122.7 40C93.1 416 0 322.9 0 208S93.1 0 208 0S416 93.1 416 208zM208 352a144 144 0 1 0 0-288 144 144 0 1 0 0 288z"
                />
            </svg>
            <router-link :to="{ name: 'Cart' }" class="cart">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 576 512">
                    <path
                        fill=" #40557e"
                        d="M0 24C0 10.7 10.7 0 24 0H69.5c22 0 41.5 12.8 50.6 32h411c26.3 0 45.5 25 38.6 50.4l-41 152.3c-8.5 31.4-37 53.3-69.5 53.3H170.7l5.4 28.5c2.2 11.3 12.1 19.5 23.6 19.5H488c13.3 0 24 10.7 24 24s-10.7 24-24 24H199.7c-34.6 0-64.3-24.6-70.7-58.5L77.4 54.5c-.7-3.8-4-6.5-7.9-6.5H24C10.7 48 0 37.3 0 24zM128 464a48 48 0 1 1 96 0 48 48 0 1 1 -96 0zm336-48a48 48 0 1 1 0 96 48 48 0 1 1 0-96z"
                    />
                </svg>
            </router-link>
            <button @click="$emit('singEvent')">sign in</button>
        </div>
    </div>
</template>

<script>
export default {
    name: "headerComponent",
    methods: {},
};
</script>

<style scoped>
.header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    color: var(--main-color);
}
.header a {
    text-decoration: none;
    font-weight: 600;
    color: inherit;
    font-size: 18px;
    border-bottom: transparent solid 2px;
    transition: color var(--main-transition),
        border-bottom-color var(--main-transition);
}

.header a.router-link-exact-active {
    color: var(--effect-color);
    border-bottom-color: var(--effect-color);
}
ul {
    display: flex;
    gap: 20px;
    list-style: none;
    color: inherit;
}

.icons {
    display: flex;
    gap: 25px;
    align-items: center;
}

button {
    align-items: center;
    -webkit-appearance: none;
    -moz-appearance: none;
    appearance: none;
    background-color: #fff;
    border-radius: 24px;
    border-style: none;
    box-shadow: rgba(0, 0, 0, 0.2) 0 3px 5px -1px,
        rgba(0, 0, 0, 0.14) 0 6px 10px 0, rgba(0, 0, 0, 0.12) 0 1px 18px 0 !important;
    box-sizing: border-box;
    color: inherit;
    cursor: pointer;
    display: inline-flex;
    fill: currentcolor !important;
    font-size: 14px;
    font-weight: 500 !important;
    height: 40px !important;
    justify-content: center;
    letter-spacing: 0.25px;
    line-height: normal;
    max-width: 100%;
    overflow: visible;
    padding: 2px 18px !important;
    position: relative;
    text-align: center;
    text-transform: none;
    transition: box-shadow var(--main-transition),
        opacity var(--main-transition), transform var (--main-transition);
    -moz-user-select: none;
    user-select: none;
    -webkit-user-select: none;
    touch-action: manipulation;
    width: auto;
    will-change: transform, opacity;
    z-index: 0;
}
button:hover {
    background: #f6f9fe;
    border: 2px solid var(--effect-color);
    outline: none;
    color: var(--effect-color);
}

svg {
    height: 22px;
}
a.cart {
    border-bottom-color: transparent !important;
    align-self: flex-end;
}
</style>
