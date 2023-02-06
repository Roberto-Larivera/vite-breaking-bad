<script>

export default {
    name: 'SingleCard',
    data() {
        return {
        }
    },
    props:{
        imgSrc:{
            type: String,
            default:'https://via.placeholder.com/60X80',
        },
        imgSrcSmall:{
            type: String,
            default:'https://via.placeholder.com/60X80',
        },
        infoName:{
            type: String,
            default:'infoName Character',
        },
        infoType:{
            type: String,
            default:'infoType Character',
        },
        infoArcheType:{
            type: String,
            default:'infoArcheType Character',
        },
        infoDesc:{
            type: String,
            default:'infoDesc Character',
        },
    }

}
</script>

<template>
    <div class="card ">
        <img :src="imgSrc" class="card-img-top w-100" :alt="infoName">
        <div class="card-body d-flex flex-column">
            <div class="h-50">
                <h5 class="card-title">
                {{infoName}}
            </h5>
            </div>
            <!-- <p class="card-text">
                {{infoDesc}}
            </p> -->
            <div class="h-50 d-flex flex-column justify-content-between">
                <p class="card-text">
                {{infoType}}
            </p>
            <p class="card-text">
                {{infoArcheType}}
            </p>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
h5{
    text-transform: uppercase;
}
</style>
