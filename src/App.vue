<template>
    <div class="container">
        <search @search="searchContent" />
        <div class="list-cards">
            <card :cards="resultListCards" />
        </div>
    </div>
</template>

<script>
import Card from "@/components/Card";
import Search from "@/components/Search";

export default {
    components: {
        Card,
        Search,
    },
    data() {
        return {
            searchQuery: "",
            resultListCards: [],
            listCards: [
                {
                    id: 1,
                    rating: 7.9,
                    name: "Дюна",
                    year: 2021,
                    genre: "фантастика, боевик",
                },
                {
                    id: 2,
                    rating: 7.3,
                    name: "Не время умирать",
                    year: 2021,
                    genre: "боевик, триллер",
                },
                {
                    id: 3,
                    rating: 7.7,
                    name: "Гнев человеческий",
                    year: 2021,
                    genre: "триллер, боевик",
                },
                {
                    id: 4,
                    rating: 7.1,
                    name: "День курка",
                    year: 2020,
                    genre: "фантастика, боевик",
                },
                {
                    id: 5,
                    rating: 6.8,
                    name: "Охота на воров",
                    year: 2018,
                    genre: "боевик, триллер",
                },
                {
                    id: 6,
                    rating: 5.5,
                    name: "Механик: Воскрешение",
                    year: 2016,
                    genre: "боевик, триллер",
                },
                {
                    id: 7,
                    rating: 6.2,
                    name: "Веном 2",
                    year: 2021,
                    genre: "фантастика, боевик",
                },
                {
                    id: 8,
                    rating: 7.3,
                    name: "Никто",
                    year: 2021,
                    genre: "боевик, триллер",
                },
                {
                    id: 9,
                    rating: 7.9,
                    name: "Дюна",
                    year: 2021,
                    genre: "фантастика, боевик",
                },
                {
                    id: 10,
                    rating: 7.3,
                    name: "Не время умирать",
                    year: 2021,
                    genre: "боевик, триллер",
                },
                {
                    id: 11,
                    rating: 7.7,
                    name: "Гнев человеческий",
                    year: 2021,
                    genre: "триллер, боевик",
                },
                {
                    id: 12,
                    rating: 7.1,
                    name: "День курка",
                    year: 2020,
                    genre: "фантастика, боевик",
                },
                {
                    id: 13,
                    rating: 6.8,
                    name: "Охота на воров",
                    year: 2018,
                    genre: "боевик, триллер",
                },
                {
                    id: 14,
                    rating: 5.5,
                    name: "Механик: Воскрешение",
                    year: 2016,
                    genre: "боевик, триллер",
                },
                {
                    id: 15,
                    rating: 6.2,
                    name: "Веном 2",
                    year: 2021,
                    genre: "фантастика, боевик",
                },
                {
                    id: 16,
                    rating: 7.3,
                    name: "Никто",
                    year: 2021,
                    genre: "боевик, триллер",
                },
            ],
        };
    },
    methods: {
        searchContent(query) {
            this.searchQuery = query.toLowerCase();
            if (query.length > 0) {
                this.resultListCards = this.listCards.filter((card) =>
                    card.name.toLowerCase().includes(this.searchQuery)
                );
            } else {
                this.resultListCards = this.listCards;
            }
        },
    },
    mounted() {
        this.resultListCards = this.listCards;
    },
};
</script>

<style>
@import "~@/assets/style/fonts.css" screen;
@import "~@/assets/style/settings.css" screen;
@import "~@/assets/style/gui-elements/buttons.css" screen;

* {
    outline: none;
    box-sizing: border-box;
    font-family: "Gilroy", sans-serif;
    font-weight: 400;
    color: #fff;
}

body,
html {
    background-color: #24201e;
}

.container {
    max-width: 1110px;
    padding: 0 15px;
    margin: 0 auto;
}

.glow-border {
    box-shadow: 0px 0px 10px 0px rgba(255, 255, 255, 0.75);
}

.list-cards {
    margin: calc(30px - 20px) -10px 0 -10px;
    border-radius: 15px;
    overflow: hidden;
}
</style>
