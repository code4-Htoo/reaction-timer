<template>
    <div class="block" v-if="showBlock" @click="endTimer">
        Click Me
    </div>
</template>

<script>
export default {
    props: ['delay'],
    data() {
        return {
            showBlock: false,
            timer:null,
            reactionTime:0
        }
    },
    mounted() {
        setTimeout(() => {
            this.showBlock = true,
            this.startTimer()
        }, this.delay);
    },
    methods: {
        startTimer(){
            this.timer = setInterval(() => {
                this.reactionTime += 10
            }, 10);
        },
        endTimer(){
            clearInterval(this.timer);
            this.$emit('end',this.reactionTime)
        }
    }
}
</script>