<script>
export default {
    name: "MainHeader",
    data() {
        return {
            navbar: ["CHARACTERS", "COMICS", "MOVIES", "TV", "GAMES", "COLLECTIBLES", "VIDEOS", "FANS", "NEWS", "SHOP"]
        };
    },
}

</script>

<template>
    <header>
        <div id="container">
            <div><img src="../assets/dc-logo.png" alt="DC LOGO"></div>
            <nav>
                <ul class="headerNavbar">
                    <a v-for="(element) in navbar" href="#">
                        <li class="nav-element" href="#"> {{ element }}</li>
                    </a>
                </ul>
            </nav>
        </div>
    </header>
</template>

<style scoped lang="scss">
@use "../styles/partials/mixins";
@use "../styles/partials/variables" as *;

header {
    background-color: $light-color;

    nav {
        align-self: stretch;
        display: flex;
        align-items: center;
    }
}

#container {
    @include mixins.d-flex-between;
    padding: 12px 0;

    img {
        width: 80%
    }

    a {
        position: relative;
        align-self: stretch;
    }

    li::after {
        content: "";
        position: absolute;
        left: 0px;
        right: 0;
        bottom: 0;
        height: 2px;
        background-color: $secondary-color;
        transform: scaleX(0);
        transition: transform 0.4s ease;
    }

    li:hover::after {
        transform: scaleX(1);
    }
}

.headerNavbar {
    @include mixins.d-flex-between;
    gap: 12px;
}

.nav-element {
    font-size: 0.8rem;
    font-weight: 600;
    color: $primary-color;

    &:hover {
        color: $secondary-color;
    }

}
</style>