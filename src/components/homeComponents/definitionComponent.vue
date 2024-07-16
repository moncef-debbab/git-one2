<template>
    <div class="definition flex-cloumn">
        <div class="content flex-cloumn">
            <div class="text flex-cloumn">
                <div class="slogun flex-cloumn">
                    <span>order your </span> <span>favourite food here </span>
                </div>
                <p class="details">
                    Choose from a diverse menu featuring a delectable array of
                    dishes crafted with the finest ingredients and culinary
                    expertise. Our mission is to satisfy your cravings and
                    elevate your dining experience, one delicious meal at a
                    time.
                </p>
            </div>
            <router-link :to="{ name: 'menu' }">
                <button>View menu</button>
            </router-link>
        </div>
    </div>
</template>

<script>
export default {
    name: "definitionComponent",
};
</script>

<style scoped>
.definition {
    background: url("/src/assets/frontend_assets/header_img.png") no-repeat;
    background-origin: border-box;
    background-size: contain;
    position: relative;
    border-radius: 10px;
    max-width: 100%;
    width: 100%;
    border: 2px solid transparent;
    height: 34vw;
    justify-content: flex-end;
    padding: 50px 60px;
    align-items: flex-start;
    box-sizing: border-box;
    gap: 20px;
    color: white !important;
}
.content {
    animation: fadeIn 3s;
    gap: 15px;
}
.text {
    text-align: left;
    max-width: 68%;
    gap: 20px;
}
.definition .slogun {
    font-weight: 600;
    font-size: 60px;
    flex-wrap: wrap;
    width: 130%;
}
.definition .slogun span {
    margin-bottom: -20px;
}

.definition .details {
    font-weight: 600;
    margin: 0;
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
    color: var(--main-color);
    cursor: pointer;
    display: inline-flex;
    fill: currentcolor !important;
    font-size: 14px;
    font-weight: 600 !important;
    height: 40px !important;
    justify-content: center;
    letter-spacing: 0.25px;
    line-height: normal;
    max-width: 100%;
    overflow: visible;
    padding: 2px 25px !important;
    position: relative;
    text-align: center;
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
</style>
