<template>
    <div class="picture">
        <canvas ref="canvas"></canvas>
    </div>
</template>
<script>
export default {

}
</script>
<style lang="scss" scoped>
.picture{
    display: block;
    margin: 20rem auto;
    width: 50vw;
    height: 50vh;
    padding: 25px;
    box-sizing: border-box;
    canvas{
        display: block;
        height: 474px;
        width: 100%;
        max-width: 1280px;
        margin: 0 auto;
        box-shadow: 4px 4px 12px 0px transparentize($color: #171717, $amount: 0.5)
    }
}
</style>