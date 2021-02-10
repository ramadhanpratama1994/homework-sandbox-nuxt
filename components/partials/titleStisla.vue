<template>
    <div>
        <div class="section-header">
            <h1>{{title}}</h1>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        title: {
            type: String,
            default: 'JUDUL HALAMAN'
        }
    }
}
</script>