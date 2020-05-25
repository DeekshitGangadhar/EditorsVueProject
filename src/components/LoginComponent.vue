<template>
    <div class="div-body">
        <div class="login-box">
            <h1>Editor Login</h1>
            <div class="textbox">
                <input type="text" placeholder="Username" name="" value="" required>
            </div>

            <div class="textbox">
                <input type="password" placeholder="Password" name="" value="" required>
            </div>

            <router-link to="/home"><input class="btn" type="button" value="LOGIN"></router-link>
        </div>
    </div>
</template>

<script>
export default {
    name: 'LoginComponent'
}
</script>

<style scoped>
    .login-box{
        margin: auto;
        margin-top: 10%;
        width: 25%;
        border: 3px solid #002C3E;
        border-radius: 30px;
        padding: 40px;
        -webkit-box-shadow: 10px 10px 10px -6px #999;
        -moz-box-shadow: 10px 10px 10px -6px #999;
        box-shadow: 10px 10px 10px -6px #999;
    }

    .login-box #image{
        text-align: center;
    }

    .login-box img{
        /* padding: 1.5% 1% 1% 5%; */
        width: 40%;
    }

    .login-box #image h1{
        font-size: 20px;
        color: white;
        border: none;
    } 

    .login-box h1{
        float: left;
        font-size: 30px;
        color: #002C3E;
        border-bottom: 3px solid #002C3E;
        margin-bottom: 30px;
    }

    .textbox{
        width: 100%;
        overflow: hidden;
        font-size: 20px;
        padding: 8px 0;
        margin: 8px 0;
        border-bottom: 1px solid #002C3E;
    }


    .textbox input{
        border: none;
        outline: none;
        background: none;
        font-size: 18px;
        width: 80px;
        float: left;
        margin: 0 10px;
    }

    .btn{
        width: 100%;
        background: none;
        border: 2px solid #002C3E;
        border-radius: 30px;
        padding: 5px;
        font-size: 18px;
        cursor: pointer;
        margin: 12px 0;
    }

    .btn:hover{
        background-color: #002C3E;
        color: white;
    }

</style>
