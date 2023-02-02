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
        </li>
    </ul>
</template>

<style scoped>
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
}
</style>