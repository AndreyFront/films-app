<template>
    <div class="app container">
        <div class="block-nav">
            <div class="block-sorting">
                <sorting-genre />
            </div>
            <search @search="searchContent" />
        </div>
        <div class="list-cards">
            <card :cards="resultListCards" />
        </div>
    </div>
</template>

<script>
import Card from "@/components/Card";
import Search from "@/components/Search";
import SortingGenre from "@/components/SortingGenre";

export default {
    components: {
        Card,
        Search,
        SortingGenre,
    },
    data() {
        return {
            searchQuery: "",
            resultListCards: [],
            listCards: [
                {
                    id: 1,
                    image: "1.webp",
                    rating: 7.9,
                    name: "Дюна",
                    year: 2021,
                    genre: "фантастика, боевик",
                },
                {
                    id: 2,
                    image: "2.webp",
                    rating: 7.3,
                    name: "Не время умирать",
                    year: 2021,
                    genre: "боевик, триллер",
                },
                {
                    id: 3,
                    image: "3.webp",
                    rating: 7.7,
                    name: "Гнев человеческий",
                    year: 2021,
                    genre: "триллер, боевик",
                },
                {
                    id: 4,
                    image: "4.webp",
                    rating: 7.1,
                    name: "День курка",
                    year: 2020,
                    genre: "фантастика, боевик",
                },
                {
                    id: 5,
                    image: "5.webp",
                    rating: 6.8,
                    name: "Охота на воров",
                    year: 2018,
                    genre: "боевик, триллер",
                },
                {
                    id: 6,
                    image: "6.webp",
                    rating: 5.5,
                    name: "Механик: Воскрешение",
                    year: 2016,
                    genre: "боевик, триллер",
                },
                {
                    id: 7,
                    image: "7.webp",
                    rating: 6.2,
                    name: "Веном 2",
                    year: 2021,
                    genre: "фантастика, боевик",
                },
                {
                    id: 8,
                    image: "8.webp",
                    rating: 7.3,
                    name: "Никто",
                    year: 2021,
                    genre: "боевик, триллер",
                },
                {
                    id: 9,
                    image: undefined,
                    rating: 7.9,
                    name: "Дюна",
                    year: 2021,
                    genre: "фантастика, боевик",
                },
                {
                    id: 10,
                    image: "2.webp",
                    rating: 7.3,
                    name: "Не время умирать",
                    year: 2021,
                    genre: "боевик, триллер",
                },
                {
                    id: 11,
                    image: "3.webp",
                    rating: 7.7,
                    name: "Гнев человеческий",
                    year: 2021,
                    genre: "триллер, боевик",
                },
                {
                    id: 12,
                    image: "4.webp",
                    rating: 7.1,
                    name: "День курка",
                    year: 2020,
                    genre: "фантастика, боевик",
                },
                {
                    id: 13,
                    image: "5.webp",
                    rating: 6.8,
                    name: "Охота на воров",
                    year: 2018,
                    genre: "боевик, триллер",
                },
                {
                    id: 14,
                    image: "6.webp",
                    rating: 5.5,
                    name: "Механик: Воскрешение",
                    year: 2016,
                    genre: "боевик, триллер",
                },
                {
                    id: 15,
                    image: "7.webp",
                    rating: 6.2,
                    name: "Веном 2",
                    year: 2021,
                    genre: "фантастика, боевик",
                },
                {
                    id: 16,
                    image: null,
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
        document.addEventListener('click', () => console.log('click'));
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
    padding: 50px 15px;
    margin: 0 auto;
}

.glow-border {
    box-shadow: 0px 0px 10px 0px rgba(255, 255, 255, 0.75);
}

.block-nav {
    display: flex;
    align-items: center;
    justify-content: space-between;
}

.block-sorting {
}

.list-cards {
    margin: calc(30px - 20px) -10px 0 -10px;
    border-radius: 15px;
    overflow: hidden;
}
</style>
