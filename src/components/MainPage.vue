<script>
export default {
    name: "MainPage",
    data() {
        return {
            ComicsList: [
                {
                    "thumb": "https://static.dc.com/2023-03/LEGIONOB_Cv1_00111_DIGITAL.jpg?w=640",
                    "price": "$19.99",
                    "series": "Action Comics",
                    "type": "comic book"
                },
                {
                    "thumb": "https://static.dc.com/2023-03/BA_Cv9_00911_DIGITAL.jpg?w=640",
                    "price": "$3.99",
                    "series": "American Vampire 1976",
                    "type": "comic book"
                },
                {
                    "thumb": "https://static.dc.com/2023-03/ST_GH_Cv3_00311_DIGITAL.jpg?w=640",
                    "price": "$16.99",
                    "series": "Aquaman",
                    "type": "graphic novel"
                },
                {
                    "thumb": "https://static.dc.com/2023-03/MS30A_Cv1_00111_DIGITAL.jpg?w=640",
                    "price": "$2.99",
                    "series": "Batgirl",
                    "type": "comic book"
                },
                {
                    "thumb": "https://static.dc.com/2023-03/MS30A_Cv1_00111_DIGITAL.jpg?w=640",
                    "price": "$3.99",
                    "series": "Batman",
                    "type": "comic book"
                },
                {
                    "thumb": "https://static.dc.com/2023-03/BMSMWF_Cv13_01311_DIGITAL.jpg?w=640",
                    "price": "$2.99",
                    "series": "Batman Beyond",
                    "type": "comic book"
                },
                {
                    "thumb": "https://static.dc.com/2023-03/NTW_Cv102_10211_DIGITAL-1.jpg?w=640",
                    "price": "$3.99",
                    "series": "Batman/Superman",
                    "type": "comic book"
                },
                {
                    "thumb": "https://static.dc.com/2023-03/FLS_Cv795_79511_DIGITAL.jpg?w=640",
                    "price": "$4.99",
                    "series": "Batman/Superman Annual",
                    "type": "comic book"
                },
                {
                    "thumb": "https://static.dc.com/2023-03/DCConnect_35-CVR.jpg?w=640",
                    "price": "$5.99",
                    "series": "Batman: The Joker War Zone",
                    "type": "comic book"
                },
                {
                    "thumb": "https://static.dc.com/2023-03/ROBIN_v3%20%28Cover%29.jpg?w=640",
                    "price": "$6.99",
                    "series": "Batman: Three Jokers",
                    "type": "comic book"
                },
                {
                    "thumb": "https://static.dc.com/2023-03/LP-ROTG_Cv1_00111_DIGITAL.jpg?w=640",
                    "price": "$4.99",
                    "series": "Batman: White Knight Presents: Harley Quinn",
                    "type": "comic book"
                },
                {
                    "thumb": "https://static.dc.com/2023-03/SM_LOST_Cv1_00111_DIGITAL.jpg?w=640",
                    "price": "$16.99",
                    "series": "Catwoman",
                    "type": "graphic novel"
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
    <div id="jumbotron">
    </div>
    <div id="container">
        <h4>CURRENT SERIES</h4>
        <div id="ComicContainer">
            <div class="Comic" v-for="comic, index in ComicsList" :key="index">
                <img :src="comic.thumb" :title="comic.series">
            </div>
        </div>
        <div>
            <button>LEARN MORE</button>
        </div>
    </div>
</template>

<style scoped lang="scss">
@use "../styles/partials/mixins";
@use "../styles/partials/variables" as *;

#jumbotron {
    position: relative;
    height: 250px;
    background-image: url("../assets/jumbotron.jpg");
    background-size: cover;
}


#container {
    position: relative;
    height: 100%;
    text-align: center;
    padding: 24px 0;

    button {
        font-size: 16px;
        background-color: $secondary-color;
        color: $light-color;
        padding: 6px 8px;
        border: none;

        &:hover {
            background-color: $light-color;
            color: $secondary-color;
        }
    }
}

h4 {
    position: absolute;
    padding: 8px;
    height: 32px;
    color: $light-color;
    background-color: $secondary-color;
    top: -16px;
}

#ComicContainer {
    padding: 32px 0;
    @include mixins.d-flex-between;
    flex-wrap: wrap;

    .Comic {
        width: calc(100% / 6);
    }

    img {
        width: 80%;
        margin: auto;
    }
}
</style>