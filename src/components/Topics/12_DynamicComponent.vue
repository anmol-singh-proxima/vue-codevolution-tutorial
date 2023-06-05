<template>
    <div>
        <h2>Dynamic Component</h2><hr/>
        <div class="dynamic-component">
            <div class="tab-menu">
                <button @click="activeTab = 'Html'">Html</button>
                <button @click="activeTab = 'Css'">Css</button>
                <button @click="activeTab = 'Javascript'">Javascript</button>
                <button @click="activeTab = 'Vue'">Vue</button>
                <button @click="activeTab = 'Python'">Python</button>
            </div>
            <component :is="activeTab" />
        </div><hr/>
        <div>
            <h3>Form</h3>
            <div class="dynamic-form">
                <div class="form-menu">
                    <button @click="activeFormTab = 'FormPage1'">Name</button>
                    <button @click="activeFormTab = 'FormPage2'">Contact</button>
                    <button @click="activeFormTab = 'FormPage3'">Password</button>
                </div>
                <div class="form-section">
                    <keep-alive>
                        <component :is="activeFormTab" />
                    </keep-alive>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import Html from './NestedComponents/DynamicComponent/Html.vue'
import Css from './NestedComponents/DynamicComponent/Css.vue';
import Javascript from './NestedComponents/DynamicComponent/Javascript.vue';
import Vue from './NestedComponents/DynamicComponent/Vue.vue';
import Python from './NestedComponents/DynamicComponent/Python.vue';
import FormPage1 from './NestedComponents/DynamicComponent/FormPage1.vue';
import FormPage2 from './NestedComponents/DynamicComponent/FormPage2.vue';
import FormPage3 from './NestedComponents/DynamicComponent/FormPage3.vue';
export default {
    name: 'DynamicComponent',
    components: {
        Html, Css, Javascript, Vue, Python, FormPage1, FormPage2, FormPage3
    },
    data() {
        return {
            activeTab: 'Html',
            activeFormTab: 'FormPage1',
        }
    }
}
</script>

<style scoped>
.tab-menu button {
    font-size: 14px;
    line-height: 1.3;
    padding: 7px 14px;
    border-top: 0;
    border-right: 1px solid rgba(100,100,100,0.5);
    border-bottom: 1px solid rgba(100,100,100,0.5);
    border-left: 0;
}
.dynamic-form {
    display: grid;
    grid-template-columns: 150px auto;
    grid-template-rows: auto;
}
.form-menu button {
    display: block;
    font-size: 14px;
    line-height: 1.3;
    padding: 7px 14px;
    border-top: 0;
    border-right: 1px solid rgba(100,100,100,0.5);
    border-bottom: 1px solid rgba(100,100,100,0.5);
    border-left: 0;
    width: 100%;
    text-align: left;
}
.form-section {
    padding-left: 15px;
}
</style>