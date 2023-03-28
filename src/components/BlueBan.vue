<script>
export default {
    name: "BannerBlu",
    data() {
        return {
            BlueArray: [
                {
                    text: "DIGITAL COMICS",
                    path: "buy-comics-digital-comics.png",
                },
                {
                    text: "DC MERCHANDISE",
                    path: "buy-comics-merchandise.png",
                },
                {
                    text: "SUBSCRIPTIONS",
                    path: "buy-comics-subscriptions.png",
                },
                {
                    text: "COMIC SHOP-LOCATOR",
                    path: "buy-comics-shop-locator.png",
                },
                {
                    text: "DC-POWER-VISA",
                    path: "buy-dc-power-visa.svg",
                }
            ],
        };
    },
    methods: {
        getImagePath: function (img) {
            return new URL(`../assets/${img}`, import.meta.url).href;
        }
    }
};

</script>

<template>
    <div class="blueban">
        <div id="container">
            <ul class="BlueCardlist">
                <li class="BlueCard" v-for="(element, index) in BlueArray" :key="index">
                    <a><img :src="getImagePath(element.path)" alt="">
                        <span> {{ element.text }} </span></a>
                </li>
            </ul>
        </div>
    </div>
</template>

<style scoped lang="scss">
@use "../styles/partials/mixins";
@use "../styles/partials/variables" as *;

.blueban {
    background-color: $secondary-color;
    position: relative;
    z-index: 999;
}

.BlueCardlist {
    @include mixins.d-flex-between;
    padding: 24px 0;
}

.BlueCard {
    color: $light-color;
    cursor: pointer;

    a {
        @include mixins.d-flex-between;
    }

    img {
        width: 40px;
        padding-right: 8px;
    }
}
</style>