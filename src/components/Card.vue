<template>
    <div class="card">
        <div class="card-image">
            <img :src="imageUrl" alt="Dynamic Image" />
            <p class="date">{{ date }}</p>
            <p class="place">
                {{ place }}
                <svg version="1.0" xmlns="http://www.w3.org/2000/svg"
                    width="16" height="16" viewBox="0 0 512.000000 512.000000"
                    preserveAspectRatio="xMidYMid meet">
                        <g transform="translate(0.000000,512.000000) scale(0.100000,-0.100000)"
                        fill="#f4f4f4" stroke="none">
                        <path d="M2430 5114 c-229 -26 -360 -54 -508 -109 -392 -147 -720 -416 -943
                        -775 -210 -339 -307 -778 -259 -1170 78 -631 528 -1501 1274 -2465 176 -228
                        403 -501 455 -548 69 -62 153 -62 222 0 52 47 279 320 455 548 671 867 1102
                        1655 1238 2267 35 157 46 259 46 423 -1 480 -193 939 -540 1285 -286 287 -623
                        460 -1020 525 -94 15 -352 27 -420 19z m247 -925 c373 -50 682 -318 783 -679
                        27 -95 37 -286 21 -390 -47 -296 -241 -556 -516 -690 -162 -79 -328 -109 -497
                        -90 -132 15 -199 34 -313 90 -275 134 -469 394 -516 690 -16 104 -6 295 21
                        390 125 446 566 741 1017 679z"/>
                        </g>
                    </svg>
            </p>
        </div>
        <div class="card-content">
            <div class="content">
                <h3 class="tittle">{{ tittle }}</h3>
                <p class="description">{{ description }}</p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Card',
    props: {
        tittle: {
            type: String,
            required: true
        },
        description: {
            type: String,
            required: true
        },
        imageUrl: {
            type: String,
            required: true
        },
        date: {
            type: String,
            required: true
        },
        place: {
            type: String,
            required: true
        }
    }
    
}
</script>

<style lang="scss" scoped>

.card {

    display: flex;
    margin: 20px; /* Espacement entre les lignes */
    width: 500px; 
    min-width: 200px;
    height: 200px;
    border-radius: 10px;
    overflow: hidden;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    &:hover {
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    }

    .card-image {
        height: 200px;
        width: 66%;
        background-color: #f4f4f4;
        position: relative;
            &::after {
            content: "";
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height:  85%; /* Ajuste la hauteur du fondu */
            background: linear-gradient(to top, rgba(0, 0, 0, 0.9), rgba(0, 0, 0, 0.3), transparent);
        }

        img{
            background-size: cover;
            background-position: center;
            overflow: hidden;
            width: 100%;
        }
        .date{
            position: absolute;
            top: 5px;
            left: 10px;
            font-size: 1.2em;
            color: #fff;
            background-color: #dcb253;
            padding: 5px 10px;
            border-radius: 5px;
            Z-index: 1;
            white-space: nowrap;
            overflow: visible;
        }
        .place{
            position: absolute;
            bottom: 0;
            right: 10px;
            font-size: 1em;
            color: #fff;
            Z-index: 1;
            text-align: right;
            svg {
                width: 16px;
                height: 16px;
                margin-right: 5px;
            }
        }
    }

    .card-content {
        width: 33%;
        padding: 16px;
        background: url('/src/assets/banner/paper.jpg') no-repeat center center;
        background-size: cover;
        background-color: rgba(255, 255, 255, 0.5);
        .content {
            .tittle {
                font-size: 1.1em;
                margin-bottom: 0.5em;
                text-align: left;
            }

            .description {
                font-size: 1em;
                color: #666;
                text-align: left;
            }
        }
    }
}
</style>