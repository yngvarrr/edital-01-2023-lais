<template>
    <section class="barra_superior">
        <div><i class="fa-regular fa-magnifying-glass"></i><input type="search" class="busca" placeholder="Busca por um assunto..."></div>
        <div class="header__inicio"><router-link to="/">Início</router-link></div>
        <div class="header__titulos">Sobre Nós</div>
        <div class="header__titulos"><router-link to="/modulos">Cursos</router-link></div>
        <div class="header__titulos"><router-link to="/parceiros">Parceiros</router-link></div>
        <div class="header__titulos"><router-link to="/transparencia">Transparência</router-link></div>
        <div class="header__titulos">Contato</div>
        <div><button class="botao__entrar">Entrar</button> <button class="botao__cadastrar">Cadastrar</button></div>
    </section>
</template>

<script>
export default {
name: 'Header-mobile'
}
</script>

<style scoped>
.header__titulos {
    font-family: 'Montserrat', sans-serif;
    font-weight: 600;
    font-size: 20px;
    color: #2F2E41;
    padding-bottom: 0.5em;
    margin: 0 0.5em;
}

.header__inicio {
    font-family: 'Montserrat', sans-serif;
    font-weight: 600;
    font-size: 20px;
    color: #707070;
    padding-bottom: 0.5em;
    margin: 0 0.5em;
}

.botao__entrar {
    width: 120px;
    height: 40px;
    border: 1px solid #707070;
    border-radius: 20px;
    background-color: white;
    color: #707070;
    cursor: pointer;
    font-family: 'Montserrat', sans-serif;
    font-size: 20px;
    font-weight: 600;
    margin: 0 0.5em;
}

.botao__cadastrar {
    width: 140px;
    height: 40px;
    left: 1679px;
    border-radius: 20px;
    border: 1px solid #707070;
    background-color: #707070;
    color: white;
    cursor: pointer;
    font-family: 'Montserrat';
    font-size: 20px;
    font-weight: 600;
}

.busca {
    background-color: transparent;
    border: 2px solid rgba(0, 0, 0, 0.2);
    border-radius: 20px;
    color: #000000;
    width: 280px;
    height: 40px;
    font-family: 'Open Sans', sans-serif;
    font-weight: 400;
    font-size: 16px;
    background-position: 1em;
    margin: 0.5em 0.5em;
}

.busca::placeholder {
    font-family: 'Open Sans', sans-serif;
    font-weight: 400;
    font-size: 16px;
    text-align: center;
    color: #545454;
    background: url("../assets/lupa.svg") no-repeat;
    background-position: 1em;
}

.logo__avasus {
    display: flex;
    width: 199.5px;
    height: 43.08px;
    padding-bottom: 0.5em;
    margin: 0 0.5em;
}

a {
    text-decoration: none;
    color: #000000;
}

</style>