<template>
    <div
        :class="[
            toggleClass
                ? 'sorting-genre sorting-genre--active'
                : 'sorting-genre',
        ]"
    >
        <div class="sorting-genre__block-active" @click="toggleSorting">
            <span class="sorting-genre__active">Жанр</span>
            <span class="sorting-genre__block-icon">
                <img
                    src="@/assets/image/icons/arrow-down.svg"
                    class="sorting-genre__icon"
                    alt=""
                />
            </span>
        </div>
        <ul class="sorting-genre__list">
            <li class="sorting-genre__list-item">фантастика</li>
            <li class="sorting-genre__list-item">боевик</li>
            <li class="sorting-genre__list-item">триллер</li>
        </ul>
    </div>
</template>

<script>
export default {
    data() {
        return {
            toggleClass: false,
        };
    },
    methods: {
        toggleSorting() {
            this.toggleClass =
                this.toggleClass === false
                    ? (this.toggleClass = true)
                    : (this.toggleClass = false);
        },
    },
};
</script>

<style scoped>
.sorting-genre {
    position: relative;
}

.sorting-genre--active .sorting-genre__list {
    opacity: 1;
    visibility: visible;
    transform: translateY(100%);
}

.sorting-genre--active .sorting-genre__active {
    opacity: 0.6;
}

.sorting-genre--active .sorting-genre__icon {
    transform: rotate(180deg);
}

.sorting-genre__block-active {
    display: flex;
    align-items: center;
    justify-content: space-between;
    min-width: 100px;
    padding: 5px;
    border: 1px solid #fff;
    border-radius: 5px;
    cursor: pointer;
}

.sorting-genre__block-active:hover > .sorting-genre__active {
    opacity: 0.6;
}

.sorting-genre__active {
    font-size: 14px;
    line-height: 18px;
    transition: 0.3s all;
}

.sorting-genre__block-icon {
    display: flex;
    margin-left: 5px;
}

.sorting-genre__icon {
    width: 12px;
    height: 12px;
    transition: 0.3s all;
}

.sorting-genre__list {
    position: absolute;
    bottom: -10px;
    left: 0;
    z-index: 10;
    opacity: 0;
    visibility: hidden;
    transform: translateY(110%);
    transition: 0.3s all;
}

.sorting-genre__list-item {
}
</style>
