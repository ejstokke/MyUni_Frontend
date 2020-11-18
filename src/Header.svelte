<script>
</script>

<div class='header flexContainer'>
    <div class="flexContainer">
        <img src="logo.png" alt="logo">
        <h3>MyUni</h3>

    </div>
    

    <div class='navBar flexContainer'>
        <input type="text" placeholder="Søk..">
        <!--
        <button>Hjem</button>
        <button>Profil</button>
        <button>Kontakt oss</button>
        -->
    </div>
</div>

<style>
    .flexContainer {
        display: flex;
        flex-direction: row;
    }

    .header {
        justify-content: space-between;
        background-color: #5DB075;
        width: 100%;
        height: 75px;
    }

    .navBar {
        margin-right: 75px;
    }

    button {
        background: transparent;
        border: 0px solid transparent;
        height: 100%;
        width: 33%;
        border-left: 1px solid rgba(0, 0, 0, .5);
        color: #2B5136;
        transition: 0.5s;
    }

    button:hover {
        background-color: #DADADA;
    }

    h3 {
        color: #2B5136;
        margin: 0px 0px 0px 10px;
        align-self: center;
    }

    img {
        height: 80%;
        align-self: center;
        margin-left: 5px;
    }

    input[type=text] {
        align-self: center;
        border: none;
        margin-left: 20px;
        font-size: 17px;
        height: 50%;
    }
</style>