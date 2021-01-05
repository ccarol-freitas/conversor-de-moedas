<template>
    <div class="legenda">
        <header class="nav">
            <div class="container">
                <label for="toggle">
                    <i class="material-icons">
                        <img src="https://img.icons8.com/android/24/000000/menu.png" />
                    </i>
                </label>
                <input type="checkbox" id="toggle" />
                <nav class="menu">
                    <h2>Legenda</h2>
                    <ul class="itens-menu">
                        <li>USD:Dolar</li>
                        <li>CAD:Dolar Canadense</li>
                        <li>BRL:Real</li>
                        <li>EUR:Euro</li>
                    </ul>
                </nav>
            </div>
        </header>
    </div>
</template>

<style scoped>
.legenda h2 {
    color: #2c3e50;
}

ul {
    list-style: none;
}
.legenda {
    position: absolute;
    width: 10px;
    right: 0%;
    height: 20px;
    top: -1px;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
}

.container {
    max-width: 960px;
    margin: 0 auto;
    display: flex;
    align-items: center;
    flex-wrap: wrap;
}

a {
    color: white;
    text-decoration: none;
}

li {
    list-style: none;
}

.nav {
    min-height: 60px;
    padding: 10px;
}
#toggle {
    display: none;
}

label {
    color: white;
    cursor: pointer;
    margin: 0 20px 0 0;
    position: absolute;
    right: 10px;
    display: none;
}

.menu {
    position: absolute;
    right: 0px;
    top: -4px;
    background: #fff;
}

.menu ul {
    display: flex;
    padding: 0;
}

.menu ul li {
    margin: 0 10px;
    cursor: pointer;
    font-weight: bold;
}

@media (max-width: 739px) {
    .container {
        flex-direction: column;
        align-items: flex-start;
        max-width: 420px;
    }

    label {
        display: block;
        cursor: pointer;
    }

    .menu {
        position: absolute;
        right: 18px;
        top: 10px;
        height: 44px;
        background: #fff;
        width: 303px;
    }

    .menu ul {
        flex-direction: column;
        display: none;
        text-align: center;
    }

    .menu ul li {
        margin: 10px 0;
        line-height: 20px;
    }

    #toggle:checked + .menu ul {
        display: block;
    }
    img {
        background: #ffff;
        padding: 10px;
        right: 290px;
        background: #ffff;
        padding: 10px;
        position: absolute;
    }

    .itens-menu {
        background: #ffff;
    }

    .menu h2 {
        margin: 10px;
    }
}
</style>
