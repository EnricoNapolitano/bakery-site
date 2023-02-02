<script>
export default {
    name: 'ProductsGallery',
    props: { gallery: Array, show: Boolean, },
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
            <div v-if="!show" class="text-hover">
                <h2>{{ item.title || 'Lorem Ipsum' }}</h2>
                <h4>{{ item.type || 'AMET CONSECTETUR' }}</h4>
                <div>{{ item.price || '' }}</div>
            </div>
            <div v-else class="text-hover">
                <h4>SELECT OPTIONS / QUICK VIEW</h4>
            </div>
        </li>
    </ul>
</template>

<style lang="scss" scoped>
@use '../../assets/scss/partials/mixins' as*;

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
        @include center-align;
        color: white
    }
}

.text-hover {
    @include h-gallery;
}
</style>