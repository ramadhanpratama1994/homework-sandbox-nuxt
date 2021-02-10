<template>
    <div>
        <title-stisla title="STUDENT" />
        <skeleton>
            <div class="form-group d-flex flex-column align-items-center">
                <input type="text" class="form-control mb-3" placeholder="Input nama lengkap student" v-model="name"/>
                <p>{{ studentName }}</p>
            </div>
        </skeleton>
    </div>
</template>

<script>
export default {
    data() {
        return {
            name: ""
        } 
    },
    computed: {
        studentName() {
            let student = {};
            student.fullname = this.name;
            student.first = this.name.split(" ")[0];
            student.last = this.name.split(" ").reverse()[0];
            return student;
        },
    },
}
</script>