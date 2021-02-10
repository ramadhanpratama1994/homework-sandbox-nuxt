<template>
    <div>
        <ul class="list-group mt-3">
                <li v-for="(item,i) in items" :key="i" class="list-group-item d-flex justify-content-between align-items-center">
                    {{item}}
                    <button type="button" @click="remove(i)" class="btn btn-outline-danger">
                        HAPUS
                    </button>
                </li>
        </ul>
    </div>
</template>

<script>
export default {
    props: {
        items: {
            type: Array,
            default: null
        }
    },
    methods: {
        remove(index) {
            this.$emit("value", index);
        },
    }
}
</script>