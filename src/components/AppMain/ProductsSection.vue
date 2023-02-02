<script>
import { data } from '../../assets/data';
import ActionCall from '../generics/ActionCall.vue';
import ProductsGallery from '../generics/ProductsGallery.vue';
import ButtonGallery from '../generics/ButtonGallery.vue';
export default {
    name: 'ProductsSection',
    data() { return { data, currIndex: 0 } },
    components: { ActionCall, ProductsGallery, ButtonGallery },
}
</script>
<template>
    <section id="products-gallery" class="container d-flex jc-between ai-center mv-section">
        <action-call :label="data.products.label" :title="data.products.title"
            :button_label="data.products.button"></action-call>
        <div class="slider">
            <products-gallery :gallery="data.gallery.slice(0, 2)"></products-gallery>
            <button-gallery b_class="b prev" i_class="fa-solid fa-angle-left"></button-gallery>
            <button-gallery b_class="b next" i_class="fa-solid fa-angle-right"></button-gallery>
        </div>
    </section>
</template>

<style lang="scss">
#products-gallery {
    ul {
        width: 800px;
        height: auto;
    }

    img {
        max-width: 100%;
    }

    .text-hover {
        h2 {
            font-size: 2.8rem;
        }
    }
}
</style>