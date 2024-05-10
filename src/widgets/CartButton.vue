<script setup>
import {IconShoppingBag} from '@tabler/icons-vue'
import {ref} from 'vue'

const url = ref('#')

axios.get('_gildsmith/apps/cart').then(response => {
    url.value = '/' + response.data.route
})
</script>

<template>
    <a :href="url" class="cartButton">
        <IconShoppingBag size="24" stroke="1.5"/>
        <span class="cartButton__text">Cart</span>
    </a>
</template>

<style scoped>
.cartButton {
    @apply flex flex-col items-center justify-center;
}

.cartButton__text {
    @apply text-sm font-semibold;
}
</style>