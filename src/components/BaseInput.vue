<template>
    <div class="mb-3">
        <label class="form-label">{{ label }}</label>
        <!-- <input type="text" class="form-control" :value="modelValue" @input="$emit('update:modelValue', $event.target.value)" /> -->
        <input v-bind="$attrs" class="form-control" v-model="value" />
    </div>
</template>

<script>
export default {
    // inheritAttrs: false, // Menonaktifkan pewarisan attribut
    props: {
        label: {
            type: String,
            required: true
        },
        modelValue: {
            type: String,
            required: true
        },
        modelModifiers: {
            type: Object,
            default: () => ([])
        }
    },
    // methods: {
    //     handleInput(event) {
    //         let value = event.target.value;

    //         if (this.modelModifiers.lowercase) {
    //             value = value.lowercase;
    //         }
    //         this.$emit('update:modelValue', value);
    //     }
    // },
    emits: ['update:modelValue'],
    computed: {
        value: {
            get() {
                return this.modelValue;
            },
            set(value) {
                if (this.modelModifiers.lowercase) {
                    value = value.toLowerCase();
                }

                this.$emit('update:modelValue', value);
            }
        }
    }
}
</script>