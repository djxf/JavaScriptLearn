<template>
    <div class="main">
        <div class="itemView" v-for="item in list" :key="item">
            {{item}}
        </div>
    </div>
    
</template>


<script>
export default {
    data () {
        return {
            list: [
                '海淀区',
                '海淀区',
                '海淀区',
                '昌平区',
                '昌平区',
                '昌平区',
                '昌平区',
            ]
        }
    },
}
</script>

<style scoped>
    .main {
        width: 100%;
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        justify-content: center;
    }
    
    .itemView {
        height: 100px;
        margin: 10px 20px 0 20px;
        border: 1px black solid;
    }
</style>