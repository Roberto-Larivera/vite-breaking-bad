<script>

export default {
    name: 'SingleCard',
    data() {
        return {
        }
    },
    props: {
        imgSrc: {
            type: String,
            default: 'https://via.placeholder.com/60X80',
        },
        imgSrcSmall: {
            type: String,
            default: 'https://via.placeholder.com/60X80',
        },
        infoName: {
            type: String,
            default: 'infoName Character',
        },
        infoType: {
            type: String,
            default: 'infoType Character',
        },
        infoArcheType: {
            type: String,
            default: 'infoArcheType Character',
        },
        infoDesc: {
            type: String,
            default: 'infoDesc Character',
        },
    }

}
</script>

<template>
    <div class="card p-2 text-center w-100">
        <img :src="imgSrc" class="card-img-top w-100" :alt="infoName">
        <div class="card-body d-flex flex-column justify-content-between">
                <h5 class="card-title">
                    {{ infoName }}
                </h5>
            <!-- <p class="card-text">
                {{infoDesc}}
            </p> -->
                <p class="card-text">
                    {{ infoType }}
                </p>
                <p class="card-text">
                    {{ infoArcheType }}
                </p>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.card{
    background-color: $color_primary;
    h5 {
        text-transform: uppercase;
        color: white;
    }
    p{
        color: $color_light-c;
    }
}
</style>
