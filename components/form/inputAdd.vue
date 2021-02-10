<template>
    <div class="input-group border mb-5 p-2">
        <input :type="type" :placeholder="name" class="form-control rounded-pill mr-3" v-model="inputItem" @keyup.enter="add">
        <div class="input-group-append">
            <button class="btn btn-outline-primary rounded-pill" @click="add">
                TAMBAHKAN
            </button>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            inputItem: "",
        }
    },
    methods: {
        add() {
            this.$emit("value", this.inputItem);
            this.inputItem = "";
        }
    },
    props: {
        name: {
            type: String,
            default: 'Text'
        },
        type: {
            type: String,
            default: 'text'
        },
    }
}
</script>