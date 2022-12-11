<template>
    <div>
        <div class="grid grid-cols-4 gap-5">
            <div v-for="p in products" :key="p.id">
                <ProductCard :product="p" />
            </div>
        </div>
    </div>
</template>

<script setup>
    definePageMeta({
        layout: 'products'
    })
    // this can fire on the server and in the browser
    // fetch products
    const { data: products } = await useFetch('https://fakestoreapi.com/products')

    // overrides the default headers in nuxt.config.ts
    // useHead({
    //     title: 'Nuxt Tutorial | Merch',
    //     meta: [
    //         { name: 'description', content: 'Nuxt 3 Merch' }
    //     ]
    // })

</script>

<style scoped>
    h2 {
        margin-bottom: 20px;
        font-size: 36px;
    }
    p {
        margin: 20px 0;
    }
</style>