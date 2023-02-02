<script>
export default {
    name: 'ProductsGallery',
    props: { gallery: Array, show: Boolean },
}
</script>
<template>
    <ul>
        <li v-for="item in gallery" :key="item.id">
            <img :src="item.src" :alt="item.title">
            <div v-if="show">
                <h3>{{ item.title }}</h3>
                <div>{{ item.price }}</div>
            </div>
            <div class="text-hover"></div>
        </li>
    </ul>
</template>

<style lang="scss" scoped>
h3 {
    padding: 15px 0;
    font-family: "Playfair Display", serif;
}

ul {
    display: flex;
    justify-content: flex-end;
}

li {
    padding: 0;
    padding-left: 20px;

    position: relative;

    &:hover .text-hover {
        display: inline-block;
    }
}

.text-hover {
    display: none;
    background-color: rgba($color: #000000, $alpha: 0.4);
    position: absolute;
    top: 0;
    bottom: 0;
    left: 20px;
    right: 0;
}
</style>