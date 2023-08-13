<template>
    <div class="result">
        <div class="title">{{results[resultText].title}}!</div>
        <div class="desc">{{results[resultText].desc}}</div>
    </div>
</template>
<script>
export default{
    name: "Results",
    props:["results","totalCorrect"],
    computed:{
        resultText(){
            let index = 0

            this.results.forEach((r,i) => {
                if(r.min <= this.totalCorrect && r.max >= this.totalCorrect){
                    index = i
                }
            })

            return index
        }
    }
}
</script>