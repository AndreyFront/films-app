<template>
    <transition-group name="cards-list" tag="div" class="animate">
        <div class="card" v-for="card in cards" :key="card.id">
            <div class="card__content">
                <div class="card__block-rating">
                    <span class="card__rating">{{ card.rating }}</span>
                </div>
                <div class="card__block-image">
                    <picture>
                        <source
                            v-if="imageCard(card.image)"
                            :srcset="
                                require('@/assets/image/posters/' + card.image)
                            "
                            type="image/webp"
                        />
                        <img
                            src="@/assets/image/posters/0.webp"
                            class="card__image"
                            alt=""
                        />
                    </picture>
                </div>
                <div class="card__inner-info-product">
                    <div class="card__block-info-product">
                        <div class="card__block-name">
                            <span class="card__name">{{ card.name }}</span>
                        </div>
                        <div class="card__block-info">
                            <span class="card__year">{{ card.year }}</span>
                            <span class="card__genre">{{ card.genre }}</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </transition-group>
</template>

<script>
export default {
    data() {
        return {};
    },
    props: {
        cards: {
            type: Array,
        },
    },
    methods: {
        imageCard(image) {
            try {
                if (require("@/assets/image/posters/" + image)) {
                    return true;
                }
            } catch (e) {
                console.log(e);
                return false;
            }
        },
    },
};
</script>

<style scoped>
.card {
    width: 16.6%;
    padding: 0 10px;
    margin-top: 20px;
}

.card__content {
    position: relative;
    cursor: pointer;
    border-radius: 5px;
    overflow: hidden;
}

.card__content:hover > .card__block-rating {
    opacity: 1;
    visibility: visible;
    transition: 1.7s all;
}

.card__content:hover > .card__inner-info-product {
    height: 100%;
    top: 0;
    opacity: 1;
    visibility: visible;
}

.card__content:hover > .card__inner-info-product .card__block-info-product {
    opacity: 1;
    visibility: visible;
    transition: 1.7s all;
}

.card__block-rating {
    position: absolute;
    z-index: 10;
    top: 10px;
    right: 10px;
    background-color: rgba(255, 255, 255, 0.8);
    height: 20px;
    width: 25px;
    display: flex;
    justify-content: center;
    align-items: center;
    opacity: 0;
    visibility: hidden;
    transition: 0.7s all;
}

.card__rating {
    font-size: 14px;
    line-height: 18px;
    color: #24201e;
}

.card__block-image {
    position: relative;
    height: 252px;
}

.card__image {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
    object-position: center;
}

.card__inner-info-product {
    position: absolute;
    top: 100%;
    left: 0;
    background: rgba(36, 32, 30, 0.5);
    background: linear-gradient(
        to top,
        rgba(36, 32, 30, 0.9),
        rgba(1, 255, 235, 0.3)
    );
    width: 100%;
    display: flex;
    justify-content: center;
    flex-direction: column;
    opacity: 0;
    visibility: hidden;
    height: 0;
    transition: 0.7s all;
}

.card__block-info-product {
    width: 90%;
    margin: 0 auto;
    opacity: 0;
    visibility: hidden;
    transition: 0.7s all;
}

.card__block-name {
}

.card__name {
    font-size: 20px;
    font-weight: 700;
    line-height: 20px;
}

.card__block-info {
    display: flex;
    flex-direction: column;
}

.card__year {
    font-size: 18px;
    line-height: 22px;
}

.card__genre {
    font-size: 12px;
    line-height: 15px;
}

.animate {
    display: flex;
    flex-wrap: wrap;
}

.cards-list-item {
    display: inline-block;
}

.cards-list-enter-active {
    transition: all 1s ease;
}

.cards-list-leave-active {
    position: absolute;
    width: 0;
    padding: 0;
    transition: all 0.5s ease;
}

.cards-list-enter-from,
.cards-list-leave-to {
    opacity: 0;
    transition: all 1s ease;
}

.cards-list-enter-from {
    transform: translateY(-30px);
}

.cards-list-move {
    transition: all 0.5s ease;
}
</style>
