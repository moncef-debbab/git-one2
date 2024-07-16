<template>
    <div class="home">
        <definitionComponent />
        <exploreComponent />
        <mobilesComponent />
        <footerComponent />
    </div>
</template>

<script>
import definitionComponent from "../components/homeComponents/definitionComponent.vue";
import exploreComponent from "../components/homeComponents/exploreComponent.vue";
import mobilesComponent from "../components/homeComponents/mobilesComponent.vue";
import footerComponent from "../components/homeComponents/footerComponent.vue";

export default {
    name: "HomeView",
    components: {
        definitionComponent,
        exploreComponent,
        mobilesComponent,
        footerComponent,
    },
};
</script>
<style scoped>
.home {
    margin-top: 50px;
}
</style>
