<script>
export default {
    name: 'ButtonGallery',
    props: { b_class: String, i_class: String }
}
</script>

<template>
    <button :class="b_class">
        <i :class="i_class"></i>
    </button>
</template>