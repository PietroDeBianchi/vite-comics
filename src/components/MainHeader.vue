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
        <div><img src="../../public/dc-logo.png" alt="DC LOGO"></div>
        <nav>
            <ul class="headerNavbar">
                <a v-for="(element) in navbar" href="#">
                    <li class="nav-element" href="#"> {{ element }}</li>
                </a>
            </ul>
        </nav>
    </header>
</template>

<style scoped lang="scss">
@use "../styles/partials/mixins";
@use "../styles/partials/variables" as *;

header {
    @include mixins.d-flex-around;
    padding: 12px 0;
    position: relative;

    img {
        width: 80%;
    }

}

.headerNavbar {
    @include mixins.d-flex-around;
}

.nav-element {
    font-size: 1rem;
    font-weight: 600;
    padding: 0 10px;
    color: $primary-color;

    &:hover {
        color: $secondary-color;
    }
}
</style>