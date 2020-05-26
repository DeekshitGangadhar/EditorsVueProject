<template>
    <div id="top-header">
        <nav>
            <input type="checkbox" id="check">
            <label for="check" id="menu-btn">
                <svg width="50" height="50">
                    <path d="M0,5 30,5" stroke="#f2f2f2" stroke-width="5" />
                    <path d="M0,14 30,14" stroke="#f2f2f2" stroke-width="5" />
                    <path d="M0,23 30,23" stroke="#f2f2f2" stroke-width="5" />
                </svg>
            </label>
            <label class="logo"><h1>X</h1><h3>plor<sub>Editors</sub></h3></label>
            <ul>
                <li><router-link to="/home">Home</router-link></li>
                <li><router-link to="/addroutes">Added Routes</router-link></li>
                <li><router-link to="/profile">Profile</router-link></li>
                <li><router-link to="/help">Help</router-link></li>
            </ul>
        </nav>
    </div>
</template>

<script>
export default {
    name: 'App_Header',
    methods: {

    }
}
</script>

<style>
    *{
        padding: 0;
        margin: 0;
        text-decoration: none;
        list-style: none;
        box-sizing: border-box;
    }

    nav {
        font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
        background: #002C3E;
        height: 80px;
        width: 100%;
    }

    label.logo h1{
        font-size: 45px;
        text-align: center;
        padding: 10px 0 0 100px;
        float: left;
        color: #F7444E;
    }

    label.logo h3{
        font-size: 25px;
        padding-top: 29px;
        text-align: center;
        float: left;
        color: white;
    }

    label.logo sub{
        font-size: 10px;
    }

    nav ul{
        float: right;
        margin-right: 50px;
    }

    nav ul li{
        display: inline;
        line-height: 80px;
        margin: 0 15px;
    }

    nav ul li a{
        color: white;
        text-transform: uppercase;
        font-weight: bold;
        padding: 7px 13px;
        border-radius: 3px;
    }

    nav ul li a:hover{
        background: rgb(2, 83, 116);
        transition: 0.3s;
    }

    #menu-btn{
        float: right;
        line-height: 80px;
        padding-top: 25px;
        margin-right: 25px;
        display: none;
        cursor: pointer;
    }

    #check{
        display: none;
    }

    @media(max-width: 858px){
        #menu-btn{
            display: block;
        }

        ul{
            position: fixed;
            width: 100%;
            height: 100vh;
            background: rgb(87, 91, 92);
            top: 80px;
            left: -100%;
            text-align: center;
            transition: all 0.2s;
        }

        nav ul li{
            display: block;
        }

        nav ul li a{
            font-size: 20px;
        }

        nav ul li a:hover{
            background: none;
            color: #002C3E;
        }

        #check:checked ~ ul{
            left: 0;
        }
    }

</style>