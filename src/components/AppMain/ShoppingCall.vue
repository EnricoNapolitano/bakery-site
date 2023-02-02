<script>
import { data } from '../../assets/data';
import ActionCall from '../generics/ActionCall.vue';
import ProductsGallery from '../generics/ProductsGallery.vue';
import ButtonGallery from '../generics/ButtonGallery.vue';
export default {
    name: 'ShoppingCall',
    data() { return { data } },
    components: { ActionCall, ProductsGallery, ButtonGallery },
}
</script>
<template>
    <section id="shopping-call" class="container d-flex jc-between ai-center mv-section">
        <div>
            <action-call :title="data.shopping.title" :paragraph="data.shopping.paragraph"
                :button_label="data.shopping.button"></action-call>
        </div>
        <div class="slider">
            <products-gallery :show="true" :gallery="data.gallery.slice(0, 4)"></products-gallery>
            <button-gallery b_class="b prev" i_class="fa-solid fa-angle-left"></button-gallery>
            <button-gallery b_class="b next" i_class="fa-solid fa-angle-right"></button-gallery>
        </div>
    </section>
</template>

<style lang="scss">
#shopping-call {
    h2 {
        font-size: 2.5rem;
    }

    .text-hover {
        h2 {
            font-size: 1.5rem;
        }

        h4 {
            font-size: 1rem;
            padding: 10px
        }
    }

    div {
        text-align: center;
    }

    ul {
        width: 1000px;
        height: auto;
    }

    li {
        padding-left: 20px;
        padding-right: 0;
    }

    img {
        max-width: 100%;
    }

    .b {
        top: 40%
    }

    .text-hover {
        bottom: 78px;
    }
}
</style>