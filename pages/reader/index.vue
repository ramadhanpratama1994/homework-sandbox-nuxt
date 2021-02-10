<template>
    <div>
        <title-stisla title="Daftar Pembaca"></title-stisla>
        <skeleton>
            <div class="row">
                <div class="col-4">
                    <input-add name="Judul Buku" @value="setValueBooks" />
                    
                </div>
                
                <div class="col-4">
                    <input-add name="Nama Pembaca" @value="setValueReaders" />
                    
                </div>

                <div class="col-4">
                    <add-select :readers="readers" :books="books" @value="setSelect"/>
                    
                </div>
            </div>
            <div class="row">
                <div class="col-4">
                    <list-item :items="books" @value="removeValueBooks" />
                </div>
                <div class="col-4">
                    <list-item :items="readers" @value="removeValueReaders" />
                </div>
                <div class="col-4">
                    <list-item :items="selectLists" @value="removeSelect" />
                </div>
            </div>
        </skeleton>
    </div>
</template>

<script>
import AddSelect from '~/components/form/addSelect.vue';
import listItem from '~/components/form/listItem.vue';
export default {
    components: { listItem, AddSelect },
    data() {
        return {
            books: [],
            readers: [],
            selectLists: []
        }
    },
    methods: {
        setValueBooks(val) {
            swal({
                text: "Anda yakin ingin menambahkan " + val + "?",
                buttons: true,
            })
            .then((books) => {
                if (books) {
                    this.books.push(val);
                }
            });
        },
        setValueReaders(val) {
            swal({
                text: "Anda yakin ingin menambahkan " + val + "?",
                buttons: true
            })
            .then((readers) => {
                if (readers) {
                    this.readers.push(val);
                }
            });
        },
        setSelect(val) {
            swal({
                text: "Anda yakin ingin menambahkan " + val + "?",
                buttons: true
            })
            .then((selectLists) => {
                if (selectLists) {
                    this.selectLists.push(val);
                }
            });
            
        },
        removeValueBooks(index) {
            swal({
                text: "Anda yakin ingin menghapusnya?",
                buttons: true
            })
            .then((books) => {
                if (books) {
                    this.books = this.books.filter((book, i) => i != index);
                }
            });
        },
        removeValueReaders(index) {
            swal({
                text: "Anda yakin ingin menghapusnya?",
                buttons: true
            })
            .then((readers) => {
                if (readers) {
                    this.readers = this.readers.filter((reader, i) => i != index);
                }
            });
        },
        removeSelect(index) {
            swal({
                text: "Anda yakin ingin menghapusnya?",
                buttons: true
            })
            .then((selectLists) => {
                if (selectLists) {
                    this.selectLists = this.selectLists.filter((selectList, i) => i != index);
                }
            });
        }
    }
}
</script>