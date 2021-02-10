<template>
    <div>
        <div class="form-group">
            <label for="inputText">input {{name}}</label>
            <input id="inputText" v-model="val" :type="type" class="form-control" :placeholder="'input ' + name">
            <p>{{val}}</p>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        name: {
            type: String,
            default: 'text'
        },
        val: {
            type: String,
            default: 'input text'
        },
        type: {
            type: String,
            default: 'text'
        },
        addClass: {
            type: String,
            default: 'text'
        }
    }
}
</script>