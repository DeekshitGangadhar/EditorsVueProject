<template>
    <div id="stoplist-div">
        <div id="stops-box">
            <ul>
                <li id="stopheadinglist"><div id="nameheading">Stop Name</div><div id="timeheading">Scheduled Time</div></li>
                <div v-bind:key="stop.stop_name" v-for="stop in stops">
                    <StopItem v-bind:stop="stop" v-on:del-stop="deleteStop" />
                </div>
            </ul>
        </div>
        <AddStop v-on:add-stop="addStop" id="add-stop-component"/>
        <div id="add-stop-div">
            <button id="addstopbtn" v-on:click="showStopForm">Add Stop</button>
            <button id="submitstopbtn" disabled v-on:click="submitStops">Submit Stops</button>
        </div>
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
            this.stops = [...this.stops, stop];

            var addstopcomponent = document.getElementById("add-stop-component");
            var addstopdiv = document.getElementById("add-stop-div");
            var stopsubmitbtn = document.getElementById("submitstopbtn");

            if(stopsubmitbtn.disabled == true && this.stops.length >= 2) {
                stopsubmitbtn.disabled = false;
            }

            addstopcomponent.style.display = "none";
            addstopdiv.style.display = "block";
        },
        deleteStop(s_name) {
            this.stops = this.stops.filter(stop => stop.stop_name !== s_name);

            if(this.stops.length < 2) {
                var stopsubmitbtn = document.getElementById("submitstopbtn");
                stopsubmitbtn.disabled = true;
            }
        },
        showStopForm() {
            var addstopcomponent = document.getElementById("add-stop-component");
            var addstopdiv = document.getElementById("add-stop-div");

            addstopcomponent.style.display = "block";
            addstopdiv.style.display = "none";
        },
        submitStops() {
            console.log("Submit stops button clicked");
        }
    }
}
</script>

<style scoped>
    #add-stop-div {
        position: relative;
        bottom: 0;
        /* height: 50px; */
        width: 100%;
        background: rgb(0, 77, 107);
        border-radius: 10px;
        border-top-left-radius: 0;
        border-top-right-radius: 0;
    }

    #add-stop-div button {
        padding: 10px;
        margin: 10px;
        color: white;
        background: #002C3E;
        border: 2px solid #002C3E;
        border-radius: 10px;
        font-weight: bold;
        font-size: 15px;
        cursor: pointer;
        outline: none;
    }

    #submitstopbtn{
        float: right;
    }

    #submitstopbtn:disabled {
        cursor: not-allowed;
        color: grey;
    }

    #add-stop-div button:hover:disabled {
        background: #002C3E;
        color: grey;
    }

    #add-stop-div button:hover {
        background: white;
        color: #002C3E;
        transition: 0.2s;
    }

    #add-stop-component{
        display: none;
    }

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