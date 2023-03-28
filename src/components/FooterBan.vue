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
    padding: 12px 0;
}

.FollowFooter {
    @include mixins.d-flex-between;

    ul {
        @include mixins.d-flex-between;
    }

    .follow {
        display: flex;
        align-items: center;
    }
}
</style>