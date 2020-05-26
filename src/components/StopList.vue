<template>
    <div id="stoplist-div">
        <div id="stops-box">
            <ul>
                <li id="stopheadinglist"><div id="nameheading">Stop Name</div><div id="timeheading">Scheduled Time</div></li>
                <!-- <li class="addedstopitem"><input type="text" class="stopname" placeholder="Stop Name" disabled><input type="text" class="stoptime" placeholder="Scheduled Time" disabled><button class="del">x</button></li> -->
                <div v-bind:key="stop.stop_name" v-for="stop in stops">
                    <StopItem v-bind:stop="stop" v-on:del-stop="deleteStop" />
                </div>
                <!-- <StopItem v-bind:key="stop" v-for="stop in stops"/> -->
            </ul>
        </div>
        <AddStop v-on:add-stop="addStop" />
    </div>
</template>

<script>
import AddStop from '@/components/AddStop.vue'
import StopItem from '@/components/StopItem.vue'

export default {
    name: 'StopList',
    components: {
        AddStop,
        StopItem
    },
    data() {
        return {
            stops: []
        }
    },
    methods: {
        addStop(stop) {
            // const { stop_name, stop_time } = stop;
            this.stops = [...this.stops, stop];
        },
        deleteStop(s_name) {
            this.stops = this.stops.filter(stop => stop.stop_name !== s_name);
        }
    }
}
</script>

<style scoped>
    #stops-box{
        height: 350px;
        width: 600px;
        background: rgb(196, 196, 196);
        border-radius: 10px;
        border-bottom-left-radius: 0;
        border-bottom-right-radius: 0;
        position: relative;
        overflow: auto;
    }

    #stopheadinglist {
        font-weight: bold;
        font-size: 17px;
        margin-bottom: 10px;
        margin-top: 10px;
    }

    #nameheading, #timeheading {
        display: inline;
        font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
    }

    #nameheading {
        margin: 0 50px 0 40px;
    }

    #timeheading {
        margin-left: 80px;
    }

    .stoptime {
        margin-left: 50px;
    }

</style>