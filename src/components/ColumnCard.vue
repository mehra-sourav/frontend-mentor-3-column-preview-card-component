<template>
    <div 
        class="column-card"
        :class="classObject"
    >
        <img :src="imgPath" :alt="cardType"/>

        <h1>{{cardType}}</h1>

        <p> {{description}}</p>

        <button>Learn More</button>
    </div>
</template>
<script>
export default {
    name: "ColumnCard",
    props: {
        cardType: String,
        isFirstCard: Boolean,
        isLastCard: Boolean
    },
    computed: {
        imgPath() {
            return require(`@/assets/images/icon-${this.cardType}.svg`);
        },
        description() {
            return this.descriptions[this.cardType];
        },
        classObject() {
            return {
                [`column-card__${this.cardType}`]: true,
                'column-card--firstcard-left-border-radius': this.isFirstCard,
                'column-card--lastcard-right-border-radius': this.isLastCard
            };
        }
    },
    data() {
        return {
            descriptions: {
                sedans: "Choose a sedan for its affordaibility and excelllent fuel economy. Ideal for cruising in the city or on your next road tryp.",
                luxury: "Cruise in the best car brands without the bloated prices. Enjoy the enhanced comfort of a luxury rental and arrive in style.",
                suvs: "Take an SUV for its spacious interior, power, and versatility. Perfect for your next family vacation and off-road adventures.",
            }
        }
    }
}
</script>
<style scoped lang="scss">
@import "@/assets/styles/ColumnCard.scss";
</style>