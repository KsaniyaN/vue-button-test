<template>
    <header>
        <div class="wrapper">
            <HelloWorld msg="Oh, a Button!" />
        </div>
    </header>

    <main>
        <div class="btns-group">
            <!-- setting disabled state based on conditions -->
            <!-- setting loading state depending on http call state aka `loading: http.state.loading`  -->
            <!-- setting custom method on click  -->
            <Button @click="" v-bind="{disabled: false, loading:false}">Standard</Button>

            <Button @click="" v-bind="{disabled: false, loading:true}">Loading</Button>

            <Button @click="" v-bind="{disabled: true, loading:false}">Disabled</Button>
        </div>
    </main>
</template>

<script setup>
import "@fontsource/inter";
import HelloWorld from '@/components/HelloWorld.vue'
import Button from "@/components/Button.vue";
</script>

<style scoped>
header {
    line-height: 1.25;
}

@media (min-width: 1024px) {
    header {
        display: flex;
        place-items: center;
    }

    header .wrapper {
        display: flex;
        place-items: flex-start;
        flex-wrap: wrap;
    }
}
</style>
