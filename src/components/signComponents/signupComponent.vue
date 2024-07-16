<template>
    <div class="sign">
        <div class="box flex-cloumn">
            <div class="signHeader">
                <h1>sing up</h1>
                <svg
                    xmlns="http://www.w3.org/2000/svg"
                    viewBox="0 0 384 512"
                    @click="$emit('singEvent')"
                >
                    <path
                        d="M376.6 84.5c11.3-13.6 9.5-33.8-4.1-45.1s-33.8-9.5-45.1 4.1L192 206 56.6 43.5C45.3 29.9 25.1 28.1 11.5 39.4S-3.9 70.9 7.4 84.5L150.3 256 7.4 427.5c-11.3 13.6-9.5 33.8 4.1 45.1s33.8 9.5 45.1-4.1L192 306 327.4 468.5c11.3 13.6 31.5 15.4 45.1 4.1s15.4-31.5 4.1-45.1L233.7 256 376.6 84.5z"
                    />
                </svg>
            </div>
            <form>
                <input type="text" placeholder="name" v-model="name" required />
                <input
                    type="email"
                    placeholder="email"
                    v-model="email"
                    required
                />

                <input
                    type="password"
                    placeholder="password"
                    v-model="password"
                    required
                />

                <button type="submit" @click="check" :disabled="isDisabled">
                    create an account
                </button>
                <div class="policy">
                    <input type="checkbox" required />
                    <p>
                        by continuing , i agree to the terms of use & privacy
                        policy
                    </p>
                </div>
            </form>
            <p>already have an account ? <span> login here </span></p>
        </div>
        <div class="Popup" v-if="weakCode">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512">
                <!--!Font Awesome Free 6.5.2 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free Copyright 2024 Fonticons, Inc.-->
                <path
                    fill="#ff4c24"
                    d="M256 512A256 256 0 1 0 256 0a256 256 0 1 0 0 512zm0-384c13.3 0 24 10.7 24 24V264c0 13.3-10.7 24-24 24s-24-10.7-24-24V152c0-13.3 10.7-24 24-24zM224 352a32 32 0 1 1 64 0 32 32 0 1 1 -64 0z"
                />
            </svg>

            <p>please enter a strong password</p>
            <svg
                @click="weakCode = !weakCode"
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 384 512"
                class="cancel"
            >
                <path
                    fill="#808080"
                    d="M376.6 84.5c11.3-13.6 9.5-33.8-4.1-45.1s-33.8-9.5-45.1 4.1L192 206 56.6 43.5C45.3 29.9 25.1 28.1 11.5 39.4S-3.9 70.9 7.4 84.5L150.3 256 7.4 427.5c-11.3 13.6-9.5 33.8 4.1 45.1s33.8 9.5 45.1-4.1L192 306 327.4 468.5c11.3 13.6 31.5 15.4 45.1 4.1s15.4-31.5 4.1-45.1L233.7 256 376.6 84.5z"
                />
            </svg>
        </div>
    </div>
</template>

<script>
import { ref, watch } from "vue";
export default {
    name: "singupForm",

    setup() {
        const password = ref();
        const name = ref("");
        const email = ref("");
        const weakCode = ref(false);
        const regEx = /[a-z0-9]\W/gi;
        const isDisabled = ref(false);

        const check = () => {
            if (regEx.test(password.value) === true) {
                weakCode.value = false;
                isDisabled.value = false;
            } else if (regEx.test(password.value) === false) {
                weakCode.value = true;
                isDisabled.value = true;
                setTimeout(function () {
                    weakCode.value = false;
                }, 3000);
            }
        };
        watch(password, check);
        return {
            password,
            name,
            email,
            check,
            weakCode,
            regEx,
            isDisabled,
        };
    },
};
</script>

<style>
.sign {
    background-color: #00000090;
    position: fixed;
    height: calc(100vh);
    width: calc(100vw);
    z-index: 999;
    left: 0%;
    top: 0%;
}
.box {
    width: 330px;
    color: #808080;
    position: absolute;
    border-radius: 8px;
    box-shadow: rgba(0, 0, 0, 0.15) 1.95px 1.95px 2.6px;
    padding: 25px 30px;
    justify-content: space-between;
    text-align: center;
    background-color: white;
    left: calc(50% - 165px);
    top: 20%;
    animation: fadeIn 0.5s;
    gap: 20px;
    font-size: 14px;
    font-weight: 600;
}
.box .signHeader {
    display: flex;
    justify-content: space-between;
    width: 100%;
    color: black;
}

.box .signHeader Svg {
    width: 12px;
}
.box .signHeader h1 {
    font-size: 22px;
}
/* @media (max-width: 910px) {
    .main {
        width: 100%;
        height: 100%;
        border-radius: 0px;
    }
} */

form {
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-direction: column;
    gap: 20px;
}
form input,
form button {
    width: 100%;
    padding: 10px;
    border-radius: 5px;
    outline: none;
    border: 1px #8080804d solid;
}

form button {
    background-color: var(--effect-color);
    color: whitesmoke;
    font-size: 16px;
    border-color: transparent;
    text-transform: none;
}

.policy {
    display: flex;
    justify-content: space-between;
    gap: 10px;
    font-size: 16px;
    width: 100%;
    align-items: center;
    text-align: left;
}
.policy input {
    height: 15px;
    width: fit-content;
    margin-top: -15px;
}
.policy p {
    font-size: 15px;
}
form + p {
    margin-top: -10px;
}
form + p > span {
    color: var(--effect-color);
}
.Popup {
    position: relative;
    right: calc(-100% + 345px);
    padding: 20px;
    background-color: white;
    z-index: 999;
    top: 3%;
    border-radius: 7px;
    color: #808080;
    font-weight: 600;
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 10px;
    box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;
    animation: fadeIn 0.5s;
    width: fit-content;
    overflow: hidden;
}
.Popup::after {
    content: "";
    position: absolute;
    width: 0%;
    background-color: #ff4c24;
    bottom: 0%;
    height: 3px;
    left: -3px;
    animation: fill 3s;
}
@keyframes fill {
    0% {
        width: 0;
    }
    100% {
        width: 103%;
    }
}

svg.cancel {
    align-self: flex-start;
    margin: -10px -10px 0 0;
    width: 9px;
}
</style>
