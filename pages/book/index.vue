<template>
    <div>
        <title-stisla title="DAFTAR BUKU"></title-stisla>
        <skeleton>
            <input-add name="Judul Buku" @value="(val) => this.books.push(val)" />
            <ul class="list-group mt-3">
                <li v-for="(book,i) in books" :key="i" class="list-group-item d-flex justify-content-between align-items-center">
                    {{book}}
                    <button type="button" @click="remove(i)" class="btn btn-outline-danger">
                        <i class="fas fa-minus"></i>
                    </button>
                </li>
            </ul>

            <input-add name="Judul Buku" @value="setValue" />
        </skeleton>
    </div>
</template>

<script>
export default {
    data() {
        return {
            books: []
        }
    },
    methods: {
        setValue(val) {
            this.books.push(val);
        },
        remove(index) {
            this.books = this.books.filter((book, i) => i != index);
        }
    }
}
</script>