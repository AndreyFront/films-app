<template>
    <div class="search">
        <form action="" v-on:submit.prevent="search" class="search__form">
            <input
                type="text"
                v-model="query"
                @search="query"
                class="search__input"
            />
            <button class="search__btn">
                <span class="search__block-icon">
                    <img
                        src="@/assets/image/icons/search.svg"
                        class="search__icon"
                        alt=""
                    />
                </span>
            </button>
        </form>
    </div>
</template>

<script>
export default {
    data() {
        return {
            query: "",
        };
    },
    methods: {
        search() {
            this.$emit("search", this.query);
        },
    },
};
</script>

<style scoped>
.search {
}

.search__form {
    display: flex;
    align-items: center;
    border: 1px solid #fff;
    border-radius: 5px;
    width: max-content;
    margin-left: auto;
    height: 32px;
}

.search__input {
    width: 250px;
    background-color: transparent;
    border: none;
    height: 100%;
    padding: 5px;
}

.search__btn {
    border: none;
    background-color: transparent;
    cursor: pointer;
    height: 100%;
    padding: 0 10px;
    transition: 0.3s all;
}

.search__btn:hover {
    opacity: 0.6;
}

.search__block-icon {
}

.search__icon {
    width: 15px;
    height: 15px;
}
</style>
