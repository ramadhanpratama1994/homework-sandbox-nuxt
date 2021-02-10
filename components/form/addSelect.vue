<template>
    <div class="border mb-5 p-2">
        <select class="form-control mb-2" id="addSelect" v-model="addSelectBooks">
            <option value="">Pilih Pembaca</option>
            <option v-for="(reader, i) in readers" :key="i" :value= reader>
                {{reader}}
            </option>
        </select>
        <select class="form-control mb-2" id="addSelect" v-model="addSelectReaders">
            <option value="">Pilih Buku</option>
            <option v-for="(book, i) in books" :key="i" :value= book>
                {{book}}
            </option>
        </select>
        <button class="btn btn-outline-primary rounded-pill" @click="add">
            TAMBAHKAN
        </button>
    </div>
</template>

<script>
export default {
    data() {
        return {
            addSelectBooks: '',
            addSelectReaders: '',
        }
    },
    props: {
        books: {
            type: Array,
            default: null
        },
        readers: {
            type: Array,
            default: null
        },
        name: {
            type: String,
            default: 'Text'
        }
    },
    methods: {
        add() {
            this.$emit("value", this.addSelectBooks + " - " + this.addSelectReaders);
        }
    },
}
</script>