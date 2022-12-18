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
            <Button @click="" v-bind="{disabled: false, loading:false}">Button</Button>

            <Button @click="" v-bind="{disabled: false, loading:true}">
                <template #left>
                    <plus-icon />
                </template>
                Button
            </Button>

            <Button @click="" v-bind="{disabled: true, loading:false}">Button</Button>
        </div>
        <div style="text-align: center; position: relative; top: -35px; left: 96px; opacity: 0.5; width: 144px;"><img
            src="@/assets/test.png" alt=""></div>

        <div class="btns-group ghost">
            <Button @click="" v-bind="{disabled: false, loading:false}">Button</Button>
            <Button @click="" v-bind="{disabled: false, loading:true}">
                <template #left>
                    <plus-icon />
                </template>
                Button
            </Button>
            <Button @click="" v-bind="{disabled: true, loading:false}">Button</Button>
        </div>
    </main>
</template>

<script setup>
import "@fontsource/inter";
import HelloWorld from '@/components/HelloWorld.vue'
import Button from "@/components/Button.vue";
import {PlusIcon} from "vue-tabler-icons";
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
