<script>
export default {
    name: "MainFooter",
    data() {
        return {
            Comics: ['Characters', 'Comics', 'Movies', 'TV', 'Games', 'video', 'News',],
            DC: ['Term of Use', 'Privacy Policy (New)', 'Ad Choises', 'Advertising', 'Jobs', 'Subscriptions', 'Talent Workshops', 'CPSC Certificates', 'Ratings', 'Shop Help', 'Contact Us'],
            Sites: ['DC', 'MAD Magazine', 'DC Kids', 'DC Universe', 'DC Power Visa'],
        }
    },
};
</script>

<template>
    <footer>
        <div id="container">
            <div class="LinksContainer">
                <div>
                    <ul>
                        <h3>DC COMICS</h3>
                        <li v-for="item in Comics"><a href="#">{{ item }}</a></li>
                    </ul>
                    <ul>
                        <h3>SHOP</h3>
                        <li><a href="#">Shop DC</a></li>
                        <li><a href="#">Shop DC Collectibles</a></li>
                    </ul>
                </div>
                <div>
                    <ul>
                        <h3>DC</h3>
                        <li v-for="item in DC"><a href="#">{{ item }}</a></li>
                    </ul>
                </div>
                <div>
                    <ul>
                        <h3>SITES</h3>
                        <li v-for="item in Sites"><a href="#">{{ item }}</a></li>
                    </ul>
                </div>
            </div>
            <div class="imgBox">
                <img src="../assets/dc-logo-bg.png" alt="">
            </div>
        </div>
    </footer>
</template>

<style scoped lang="scss">
@use "../styles/partials/mixins";
@use "../styles/partials/variables" as *;

footer {
    background-image: url("../assets/footer-bg.jpg");
    background-size: cover;
}

#container {
    @include mixins.d-flex-between;
    height: 400px;
}

.LinksContainer {
    display: flex;
    justify-content: center;
    align-items: flex-start;

    ul {
        padding: 0 8px 12px 0;
    }

    h3 {
        color: $light-color;
        padding-bottom: 8px;
    }

    a {
        font-size: 12px;
        color: $primary-light-color;
    }
}

.imgBox {
    position: relative;
    height: 100%;
    width: 500px;

    img {
        position: absolute;
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
    }
}
</style>