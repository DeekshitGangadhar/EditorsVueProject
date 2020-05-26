<template>
    <div id="addstop-div">
        <div id="add-stop">
            <form id="details-form">
                <div id="stop-name">
                    <select name="stops" id="stop-menu">
                        <option value="" disabled selected hidden>Choose stop...</option>
                        <option value="Trivandrum">Trivandrum</option>
                        <option value="East Fort">East Fort</option>
                        <option value="Statue">Statue</option>
                        <option value="Palayam">Palayam</option>
                        <option value="Museum">Museum</option>
                        <option value="Vellayambalam">Vellayambalam</option>
                    </select>
                </div>
                <label id="time-label">Scheduled <br/> time :</label>
                <div id="stop-time">
                    <input type="time" id="time-input">
                </div>
                <div id="stop-set">
                    <input type="button" value="+ STOP" id="add-stop-btn">
                </div>
            </form>
        </div>
    </div>
</template>

<script>
export default {
    
}
</script>

<style scoped>
    #add-stop {
        position: absolute;
        bottom: 0;
        /* height: 50px; */
        width: 100%;
        background: rgb(0, 77, 107);
        border-radius: 10px;
        border-top-left-radius: 0;
        border-top-right-radius: 0;
    }

    #details-form {
        /* padding: 8px; */
        display: flex;
    }

    #stop-name {
        border: 3px solid #002C3E;
        border-radius: 5px;
        background: white;
        width: 27%;
        float: left;
        padding: 10px;
        /* margin-bottom: 5px; */
        margin: 10px;
    }

    #stop-menu {
        border: none;
        width: 100%;
        background: none;
        cursor: pointer;
    }

    select:focus, input:focus {
        outline: 0;
    }

    #stop-time {
        padding: 10px;
        border: 3px solid #002C3E;
        border-radius: 5px;
        width: 23%;
        background: white;
        margin: 10px;
    }

    #time-label {
        color: white;
        margin: 10px;
        margin-top: 16px;
        font-size: 14px;
        font-weight: bold;
        text-align: center;
    }

    #time-input {
        width: 100%;
        border: none;
        background: none;
        text-align: center;
        font-size: 15px;
        cursor: pointer;
    }

    #stop-set {
        margin: 15px;
        margin-left: 30px;

    }

    #add-stop-btn {
        padding: 10px 20px 10px 20px;
        color: white;
        background: #002C3E;
        border: 2px solid #002C3E;
        border-radius: 10px;
        font-weight: bold;
        font-size: 15px;
        cursor: pointer;
    }

    #add-stop-btn:hover {
        background: white;
        color: #002C3E;
    }

</style>