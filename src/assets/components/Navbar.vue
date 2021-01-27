<template>
    <b-navbar>
        <template #brand>
            <b-navbar-item tag="router-link" :to="{ path: '/' }">
                <img
                    src="../logo.jpg"
                    alt="Lightweight UI components for Vue.js based on Bulma"
                >
            </b-navbar-item>
        </template>
        <template #start>
            <b-navbar-item href="#">
                Home
            </b-navbar-item>
            <b-navbar-item href="#">
                Documentation
            </b-navbar-item>
            <b-navbar-dropdown label="Info">
                <b-navbar-item href="#">
                    About
                </b-navbar-item>
                <b-navbar-item href="#">
                    Contact
                </b-navbar-item>
            </b-navbar-dropdown>
        </template>

        <template #end>
            <b-navbar-item tag="div">
                <div class="buttons">
                    <a class="button btn-color" :class="{'is-dark': validateTheme('dark'), 'is-light': validateTheme('light')}">
                        <strong>Sign up</strong>
                    </a>
                    <a class="button " :class="{'is-dark': validateTheme('dark'), 'is-light': validateTheme('light')}">
                        Log in
                    </a>
                </div>
            </b-navbar-item>
        </template>
    </b-navbar>
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
<style lang="sass">

</style>