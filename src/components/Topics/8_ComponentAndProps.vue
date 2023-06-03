<template>
    <div>
        <h2>Component And Props</h2><hr/>
        <div>
            <h3>Articles</h3>
            <div v-for="article in articles" :key="article.id">
                <Article :article="article" />
            </div>
        </div>
    </div>
</template>

<script>
import Article from './NestedComponents/Article.vue';
export default {
    name: 'ComponentAndProps',
    components: {
        Article,
    },
    data() {
        return {
            articles: [
                {
                    id: 1,
                    title: "Article Title 1",
                    author: "Anmol Singh",
                    date: "25/07/2022",
                    content: "Alksjkf slkdjfkds skdjfkdjs ksdfjksdj skdga shgdajdyada, akjshdadusakdjjashdjahds ajshdkjashdjahds, askjhdkjahdjhasjda. askjdhjashdjasd ajsdhjahsd akjdhjasd, aksjdhasjhdkja jakdhiuwehwu askjhdajksd, akjdha dfhjdfrhjfhdf, sdhsjkdhjshdd sjhdjs qjwqj lklqwoqw jshdkwue ksjdhwue skjhdwkuehw ksjdhwuehw ksjhdkwhuwh, jdhgwjgeyweweuhwe.",
                },
                {
                    id: 2,
                    title: "Article Title 2",
                    author: "Anmol Singh",
                    date: "20/09/2022",
                    content: "Alksjkf slkdjfkds skdjfkdjs ksdfjksdj skdga shgdajdyada, akjshdadusakdjjashdjahds ajshdkjashdjahds, askjhdkjahdjhasjda. askjdhjashdjasd ajsdhjahsd akjdhjasd, aksjdhasjhdkja jakdhiuwehwu askjhdajksd, akjdha dfhjdfrhjfhdf, sdhsjkdhjshdd sjhdjs qjwqj lklqwoqw jshdkwue ksjdhwue skjhdwkuehw ksjdhwuehw ksjhdkwhuwh, jdhgwjgeyweweuhwe.",
                }
            ]
        }
    }
}
</script>

<style scoped>

</style>