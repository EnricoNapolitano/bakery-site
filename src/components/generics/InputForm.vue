<script>
export default {
    name: 'InputForm',
    data() { return { value: '', saveValue: '' } },
    props: { placeholder: String, text: String },
    methods: {
        getValue() {
            this.saveValue = this.value;
            this.value = '';
        }
    }
}
</script>
<template>
    <form @submit.prevent="getValue">
        <input type="text" v-model.trim="value" :placeholder="placeholder || 'Type here...'">
        <button class="btn"> {{ text || 'SEND' }}</button>
    </form>
</template>

<style lang="scss" scoped>
@use '../../assets/scss/partials/variables' as*;

input {
    width: 350px;
    height: 40px;
    padding-left: 20px;

    border: 1px solid $violet3;
    border-radius: 5px;

    &:focus {
        outline: none;
        border-color: $violet4;
    }
}

button {
    height: 40px;
    padding: 0 20px;
    margin-left: 10px;
}
</style>