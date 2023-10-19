<template class="all">
    <div class="container">
        <button class="myBtn" @click="increment"> Counter </button>
        <div class="emojis"> {{ arrayEmojis }}</div>
    </div>
</template>

<script>
import { ref, computed } from 'vue';

export default{
    props:{
        emoji: { type: String, default: '😬' }
    },
    setup(props){
        const counter = ref(0)
        const increment = () => counter.value++
        
        const arrayEmojis = computed (() =>
        Array.from(new Array(counter.value), () => props.emoji).join(''))

        return{counter, increment, arrayEmojis}
    }
}
</script>

<style scoped>

.all{
    display: flex;
    flex-direction: column;
    gap: 50px;
   
}
.container{ 
    margin-left: 900px;
    width: 200px;
}

.myBtn{
    width: 200px;
    background-color:antiquewhite;
    border-radius: 5px;
    cursor: pointer;
    padding: 5px;
}
</style>