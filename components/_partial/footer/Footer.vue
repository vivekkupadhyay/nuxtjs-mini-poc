<template>
    <footer class="footer-section section-padding">
        <div class="container">
            <Logo /> 
            <div class="row footer-copyright">
                <div class="col-md-12">
                    © COPYRIGHT 2020 | INTO UNIVERSITY PARTNERSHIPS LTD AND IUP 2 LLP
                    &nbsp;|&nbsp;
                    沪ICP备14028023号-3
                    &nbsp;|&nbsp;
                    <a href="/" title="Privacy">Privacy</a>
                    &nbsp;|&nbsp;
                    <a href="/" title="Terms">Terms</a>
                    &nbsp;|&nbsp;
                    <a href="/" title="Sitemap">Sitemap</a>
                    &nbsp;|&nbsp;
                    <a href="/" title="Cookies Policy">Cookies Policy</a>
                    &nbsp;|&nbsp;
                    <a href="/" title="Governance">Governance</a>
                </div>
            </div>
        </div>
    </footer>
</template>

<script>
import Logo from '../header/Logo'
export default {
    name: 'footerSection',
    components: {
        Logo
    }
}
</script>