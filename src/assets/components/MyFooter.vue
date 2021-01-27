<template>
    <footer class="footer is-centered">
        <div class="content has-text-centered" :class="{'has-background-black has-text-primary-light': validateTheme('dark')}">
            <p>
            Landin Page por John Jairo González</a>. The source code is licensed
            <a href="http://opensource.org/licenses/mit-license.php">MIT</a>. The website content
            is licensed <a href="http://creativecommons.org/licenses/by-nc-sa/4.0/">CC BY NC SA 4.0</a>.
            </p>
        </div>
    </footer>
</template>
<script>
export default {
    props:{
        theme:String
    },
    methods:{
        validateTheme: function(name){
            if(name===this.theme)
                return true
            return false
        }
    }
}
</script>
<style lang="scss">

</style>