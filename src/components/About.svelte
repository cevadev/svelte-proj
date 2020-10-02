<script>
    let someText = `Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent felis velit, malesuada sed erat nec, vestibulum dictum dolor. Mauris eget iaculis justo. Maecenas eros dui, malesuada nec dapibus egestas, posuere ut metus. Fusce dignissim dapibus congue. Nulla lobortis, velit quis molestie condimentum, nulla tortor facilisis metus, sit amet ullamcorper risus mi vitae elit. Aenean volutpat dui urna, non efficitur neque maximus eget. Donec fringilla non libero dapibus mattis.`;

    //manejamos un contador
    let count = 0;
    function handleClick(){
        count += 1;
    }

    //Manejando condicionales
    let styles = { darkMode: false }

    //funcion que al dar click se activa el darkmode
    function toogle(){
        styles.darkMode = !styles.darkMode //si el valor de darkMode es false pasalo a true o viceversa

        //Trabajamos con el DOM y activamos el selector .class dark-mode para aplicar los estilos al body
        window.document.body.classList.toggle("dark-mode")
    }
</script>

<style>
    p{
        color: var(--theme-color);
    }
</style>

<div class="About">

    <!--Condicional para mostrar o no el texto-->
    {#if !styles.darkMode}
        <p>{someText}</p>
    {:else}
        <p>Hello dark mode</p>
    {/if}

    
    <button on:click={handleClick}>Click me! {count === 0 ? '' : count}</button>
    
    <!--boton que implementa la funcionalidad dark-mode-->
    <button on:click={toogle}>DarkMode</button>
</div>