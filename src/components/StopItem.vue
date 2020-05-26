<template>
    <div>
        <div class="addedstopitem">
            <input type="text" class="stopname" placeholder="Stop Name" disabled v-bind:value="stop.stop_name">
            <input type="text" class="stoptime" placeholder="Scheduled Time" disabled v-bind:value="stop.stop_time">
            <button @click="$emit('del-stop', stop.stop_name)" class="del">x</button>
        </div>
    </div>
</template>

<script>
export default {
    name: 'StopItem',
    props: ['stop']
}
</script>

<style scoped>
    .addedstopitem {
        border-bottom: 1px solid #002C3E;
        border-radius: 5px;
    }

    .stopname, .stoptime{
        font-family: 'Courier New', Courier, monospace;
        display: inline;
        margin: 15px 10px;
        padding: 5px;
        overflow: hidden;
    }

    .stoptime {
        margin-left: 50px;
    }

    .del {
        margin: 10px;
        color: white;
        background: red;
        border: 1px solid red;
        margin-left: 100px;
        border-radius: 100px;
        padding: 5px 10px;
        cursor: pointer;
        font-size: 10px;
        font-weight: bold;
    }

    .del:hover {
        color: red;
        background: white;
    }
</style>