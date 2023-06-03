<template>
    <div>
        <h2>Provide and Inject APIs</h2><hr/>
        <div class="provide-and-inject">
            <div class="data">
                <h3>Data</h3>
                <p>The Data provided and injected in the Component tree is as follows:</p>
                <div v-for="(item, index) in data" :key="index">
                    <p>{{ index + 1 }}. {{ item }}</p>
                </div>
            </div>
            <div class="data-info">
                <h3>Data Info</h3>
                <p>Data is provided from: <span>Home.vue</span></p>
                <p>Data is injected into: <span>ProvideAndInject.vue</span></p>
                <p>Full Path: <span>Home.vue > MainSection.vue > ProvideAndInject.vue</span></p>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'ProvideAndInject',
        inject: ['data']
    }
</script>

<style scoped>
.provide-and-inject p {
    font-size: 14px;
}
.provide-and-inject p span {
    font-size: 13px;
    font-style: italic;
    font-weight: 600;
}
</style>