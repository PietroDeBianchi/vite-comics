<script>
export default {
    name: "FooterBan",
    data() {
        return {
            SocialImg: ['footer-facebook.png', 'footer-periscope.png', 'footer-pinterest.png', 'footer-twitter.png', 'footer-youtube.png'],
        };
    },
    methods: {
        getImagePath: function (image) {
            return new URL(`../assets/${image}`, import.meta.url).href;
        }
    }
}
</script>

<template>
    <footer>
        <div id="container">
            <div class="FollowFooter">
                <button>Sign Up Now!</button>
                <div class="follow">
                    <h4>FOLLOW US</h4>
                    <ul>
                        <li v-for="image, index in SocialImg" :key="index">
                            <a href="#"><img :src="getImagePath(image)" alt="Immmagine"></a>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </footer>
</template>

<style scoped lang="scss">
@use "../styles/partials/mixins";
@use "../styles/partials/variables" as *;

footer {
    background-color: $primary-color;
    padding: 24px 0;
}

.FollowFooter {
    @include mixins.d-flex-between;

    button {
        font-size: 16px;
        background-color: $primary-color;
        color: $light-color;
        border: 2px solid $secondary-color;
        padding: 6px 8px;

        &:hover {
            background-color: $light-color;
            color: $secondary-color;
            border: 2px solid $secondary-color;
        }
    }

    .follow {
        display: flex;
        align-items: center;

        h4 {
            font-size: 20px;
            padding-right: 8px;
            color: $secondary-color;
        }
    }

    ul {
        @include mixins.d-flex-between;
        gap: 8px;
    }
}
</style>