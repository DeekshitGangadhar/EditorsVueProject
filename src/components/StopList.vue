<template>
    <div id="stoplist-div">
        <div id="stops-box">
            <AddStop />
        </div>
    </div>
</template>

<script>
import AddStop from '@/components/AddStop.vue'

export default {
    name: 'StopList',
    components: {
        AddStop
    }
}
</script>

<style scoped>
    #stops-box{
        height: 300px;
        width: 600px;
        background: grey;
        border-radius: 10px;
        position: relative;
    }
</style>