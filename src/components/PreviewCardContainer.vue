<template>
    <main class="preview-card-container">
        <ColumnCard
            v-for = "(card, idx) in cardsList" 
            :key="card"
            :cardType="card" 
            :isFirstCard="idx == 0"
            :isLastCard="idx == cardsList.length - 1"
        />
    </main>
</template>
<script>
import ColumnCard from './ColumnCard.vue';
export default {
    name: "PreviewCardContainer",
    components: {
        ColumnCard
    },
    data() {
        return {
            cardsList: ["sedans", "suvs", "luxury"],
            cardsListTest: ["suvs"]
        }
    }
}
</script>
<style scoped lang="scss">
@import "@/assets/styles/PreviewCardContainer.scss";
</style>