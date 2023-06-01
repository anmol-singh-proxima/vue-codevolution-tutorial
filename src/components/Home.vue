<template>
    <div class="home-page">
        <div class="header">
            <Header />
        </div>
        <div class="section">
            <div class="menu-section">
                <MenuSection 
                :menuItems="menuItems"
                :currentMenuIndex="currentMenuIndex"
                :setMenuIndex="setMenuIndex"/>
            </div>
            <div class="main-section">
                <MainSection 
                :menuItems="menuItems"
                :currentMenuIndex="currentMenuIndex"
                :setMenuIndex="setMenuIndex"/>
            </div>
        </div>
    </div>
</template>

<script>
/* eslint-disable */
import Header from './Header.vue';
import MenuSection from './MenuSection.vue';
import MainSection from './MainSection.vue';
export default {
    name: 'Home',
    components: {
        Header,
        MenuSection,
        MainSection,
    },
    data() {
        return {
            menuItems: [
                'Binding',
                'Conditional Rendering',
                'List Rendering',
                'Event Handling',
            ],
            currentMenuIndex: 0,
        }
    },
    methods: {
        setMenuIndex(index) {
            this.currentMenuIndex = index
        }
    }
}
</script>

<style>
.home-page {
    padding: 0;
    margin: 0;
}
.header {
    width: 100%;
}
.section {
    width: 100%;
    display: block;
    clear: both;
    text-align: left;
}
.menu-section {
    width: 20%;
    float: left;
}
.main-section {
    width: 80%;
    float: right;
    border-left: 1px solid #888;
}

</style>