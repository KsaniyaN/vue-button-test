<template>
    <button v-bind="{name, disabled: isDisabled, loading: isLoading}"
            type="button"
            :class="{ disabled: isDisabled, loading: isLoading }"
            @click.stop="click">
        <span class="left" v-if="!!$slots.left"><slot name="left"></slot></span>
        <span class="name"><slot /></span>
        <span class="loader" v-show="isLoading">
            <Loader />
        </span>
        <span class="right" v-if="!!$slots.right"><slot name="right"></slot></span>
    </button>
</template>

<script>
import Loader from "@/components/Loader.vue";

export default {
    components: {Loader},
    props: {
        loading: {type: Boolean, default: false},
        disabled: {type: Boolean, default: false}
    },

    data() {
        return {
            isDisabled: this.disabled,
            isLoading: this.loading
        }
    },

    methods: {
        click(e) {
            if (!e.detail || e.detail === 1) {  // prevent multiple clicks
                console.log("I'm clicked");
            }
        }
    }
};
</script>

<style scoped>

button {
    display: flex;
    align-items: center;

    background: var(--btn-base-background);
    border: none;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(10, 14, 20, 0.08);

    color: #fff;

    font-family: "Inter", sans-serif;
    font-style: normal;
    font-weight: 500;
    font-size: 13px;
    line-height: 20px;

    padding: 10px 13px;
}

button:hover {
    background: linear-gradient(0deg, rgba(0, 0, 0, 0.2), rgba(0, 0, 0, 0.2)), var(--btn-base-background);
}

button:active {
    background: linear-gradient(0deg, rgba(0, 0, 0, 0.4), rgba(0, 0, 0, 0.4)), var(--btn-base-background);
}

button:focus {
    outline: 1px solid var(--btn-base-background);
    outline-offset: 3px;
}

button.disabled {
    background: linear-gradient(0deg, rgba(255, 255, 255, 0.6), rgba(255, 255, 255, 0.6)), var(--btn-base-background);
}

.left {
    padding-right: 17px;
}

.loading .left,
.loading .name {
    display: none;
}

.loader {
    display: inline-block;
    margin-left: 0;
    position: relative;
    top: 1px;
}

.ghost button {
    background: var(--btn-ghost-background);
    border: 1px solid var(--btn-ghost-border-color);
    color: var(--btn-ghost-font-color);
}

.ghost button:hover {
    border-color: var(--btn-ghost-border-color--hover);
}

.ghost button:active {
    border-color: var(--btn-ghost-border-color--active);
}

.ghost button.disabled {
    background: var(--btn-ghost-background--disabled);
    color: var(--btn-ghost-font-color--disabled);
}

.ghost .loader {
    fill: #626A7A;
}

@media (min-width: 1024px) {
    button {
        padding: 10px 20px;
    }

    .left {
        position: relative;
        top: 3px;
    }

    .loading .left,
    .loading .name {
        display: inline;
    }

    .loader {
        margin-left: 8px;
        top: 2px;
    }
}

</style>