<template>
    <div class="page">
        <Bar/>
        <Content/>
    </div>
</template>

<script>
import Bar from '../components/Navigation'
import Content from '../components/MainContent'
export default {
    components:{
        Bar,
        Content
    }
}
</script>

<style scoped>
.page{
    margin: 0;
}
</style>