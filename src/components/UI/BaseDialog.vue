<template>
<teleport to="body">
     <div @click="$emit('close')">
        <dialog open>
            <header>
                <slot name="header">
                    <h2> {{ title }} </h2>
                </slot>
            </header>
            <section>
                <slot></slot>
            </section>
            <menu>
                <slot name="actions">
                    <base-button @click="$emit('close')">Close</base-button>
                </slot>
            </menu>
        </dialog>
    </div>
</teleport>  
</template>

<script>
import BaseButton from './BaseButton.vue';

export default{
    components: {BaseButton},
    props: {
        title: {
            type: String,
            required: false
        }
    },
    emits: ['close']
}
</script>