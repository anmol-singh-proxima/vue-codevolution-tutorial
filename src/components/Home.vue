<template>
    <div class="home-page">
        <div class="header">
            <Header />
        </div>
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
        <div class="footer">
            <Footer />
        </div>
    </div>
</template>

<script>
/* eslint-disable */
import Header from './Header.vue';
import MenuSection from './MenuSection.vue';
import MainSection from './MainSection.vue';
import Footer from './Footer.vue';
export default {
    name: 'Home',
    components: {
        Header,
        MenuSection,
        MainSection,
        Footer,
    },
    data() {
        return {
            menuItems: [
                'Binding',
                'Conditional Rendering',
                'List Rendering',
                'Event Handling',
                'Form Handling',
                'Computed Properties',
                'Watchers',
                'Component and Props',
                'Provide and Inject',
                'Custom Component Event',
                'Slots',
                'Dynamic Component',
                'Teleport Component',
                'Http Request',
            ],
            currentMenuIndex: 0,
        }
    },
    methods: {
        setMenuIndex(index) {
            this.currentMenuIndex = index
        }
    },
    provide() {
        return {
            data: this.menuItems
        }
    }
}
</script>

<style>
.home-page {
    padding: 0;
    margin: 0;
    display: grid;
    /* grid-template-columns: 25% 25% 25% 25%; */
    grid-template-columns: 20% 20% 20% 20% 20%;
    grid-template-rows: 50px auto 50px;
    min-height: 100vh;
}
.header {
    grid-column: 1/6;
    grid-row: 1/2;
}
.menu-section {
    grid-column: 1/2;
    grid-row: 2/3;
}
.main-section {
    grid-column: 2/6;
    grid-row: 2/3;
    border-left: 1px solid #888;
}
.footer {
    grid-column: 1/6;
    grid-row: 3/4;
    margin-top: auto;
}
</style>