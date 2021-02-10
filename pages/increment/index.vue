<template>
    <div>
        <title-stisla title="INCREMENT"></title-stisla>
        <skeleton>
            <div id="watch-example">
                <p>Ask a yes/no question:
                    <input v-model="question" />
                </p>
                <p>{{ answer }}</p>
            </div>

            <div class="text-right">
                <button class="btn btn-secondary" @click="minus">
                    <i class="fas fa-minus"></i>
                    Decrement
                </button>
                <button class="btn btn-primary" @click="add">
                    <i class="fas fa-plus"></i>
                    Increment
                </button>
            </div>
            <div class="d-flex justify-content-center h-100">
                <div class="d-flex align-items-center">
                    <h1>{{myIncrement}}</h1>
                </div>
            </div>
        </skeleton>
    </div>
    
</template>

<script>
export default {
    data() {
        return {
            increment: 0,
            question: '',
            answer: 'Questions usually contain a question mark. ;-)'
        }
    },
    watch: {
 // whenever question changes, this function will run
        question(newQuestion, oldQuestion) {
            if (newQuestion.indexOf('?') > -1) {
                this.getAnswer()
            }
        }
    },

    computed: {
        myIncrement() {
            return this.increment == 3
            ? "UDAH BANYAK " + this.increment
            : this.increment;
        }
    },
    methods: {
        add() {
            if (this.increment < 3 )
            this.increment++;
        },
        minus() {
            if (this.increment > 0)
            this.increment--;
        },
        getAnswer() {
            this.answer = 'Thinking...'
            this.$axios
                .get('https://yesno.wtf/api')
                .then(response => {
                    this.answer = response.data.answer
                }).catch(error => {
                    this.answer = 'Error! Could not reach the API. ' + error
                })
            }
    }
}
</script>