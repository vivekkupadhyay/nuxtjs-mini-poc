<template>
   <header class="header-section text-center if-blue-bg">
        <div class="container">
            <a href="/" title="IntoFuture">
                <Logo />
            </a>
        </div>
   </header>
</template>

<script>
import Logo from './Logo'
export default { 
    name: 'headerSection',
    components: {
        Logo
    }
}
</script>