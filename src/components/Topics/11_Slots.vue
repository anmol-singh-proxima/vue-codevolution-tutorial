<template>
    <div>
        <h2>Slots</h2><hr/>
        <!-- Cards with single Slot -->
        <h3>Single Slot Cards</h3>
        <div class="single-slot-cards">
            <!-- First Card -->
            <SingleSlotCard />
            <!-- Second Card -->
            <SingleSlotCard>
                <div class="user-info">
                    <h4>User Info</h4><hr/>
                    <p>Name: {{ user.name }}</p>
                    <p>Email: {{ user.email }}</p>
                    <p>Company: {{ user.company }}</p>
                    <p>Work Experience: {{ user.workExp }}</p>
                </div>
            </SingleSlotCard>
            <!-- Third Card -->
            <SingleSlotCard>
                <div class="user-image">
                    <h4>User Image</h4><hr/>
                    <img src="../../assets/profile_pic.jpg" alt="" />
                </div>
            </SingleSlotCard>
        </div><hr/>
        <!-- Cards with multiple Slots -->
        <h3>Multiple Slot Cards</h3>
        <div class="multiple-slot-cards">
            <MultipleSlotCard v-for="item in items" :key="item.id">
                <template v-slot:header>
                    <span class="item-title">{{ item.title }}</span>
                </template>
                <template v-slot:content>
                    <img :src="item.img" :alt="item.title"/>
                    <p>Price: ${{ item.price }}</p>
                </template>
                <template v-slot:footer>
                    <button class="cart-btn">Add To Cart</button>
                    <button class="buy-btn">Buy Now</button>
                </template>
            </MultipleSlotCard>
        </div><hr/>
        <!-- Slot Props -->
        <h3>Slot Props</h3>
        <div class="slot-props">
            <SlotPropComp>
                <template v-slot:default="slotProps">
                    <p class="title">{{ slotProps.article.title }}</p>
                    <p class="author-date">By <span>{{ slotProps.article.author }}</span><br/>On <span>{{ slotProps.article.date }}</span></p>
                    <p class="content">{{ slotProps.article.content }}</p>
                    <p>Likes: {{ slotProps.article.noOfLikes }}</p>
                    <p>Dislikes: {{ slotProps.article.noOfDislikes }}</p>
                </template>
            </SlotPropComp>
            <SlotPropComp>
                <template v-slot:default="slotProps">
                    <p class="title">{{ slotProps.article.title }}</p>
                    <p class="author-date">By <span>{{ slotProps.article.author }}</span><br/>On <span>{{ slotProps.article.date }}</span></p>
                    <p class="content">{{ slotProps.article.content }}</p>
                    <button>Likes: {{ slotProps.article.noOfLikes }}</button>
                    <button>Dislikes: {{ slotProps.article.noOfDislikes }}</button>
                </template>
            </SlotPropComp>
            <SlotPropComp>
                <template v-slot:default="slotProps">
                    <p class="title">{{ slotProps.article.title }}</p>
                    <p class="author-date">By <span>{{ slotProps.article.author }}</span> On <span>{{ slotProps.article.date }}</span></p>
                    <p class="content">{{ slotProps.article.content }}</p>
                    <button>Likes: {{ slotProps.article.noOfLikes }}</button>
                    <button>Dislikes: {{ slotProps.article.noOfDislikes }}</button>
                </template>
            </SlotPropComp>
        </div>
    </div>
</template>

<script>
/* eslint-disable */
import SingleSlotCard from './NestedComponents/Slots/SingleSlotCard.vue';
import MultipleSlotCard from './NestedComponents/Slots/MultipleSlotCard.vue';
import SlotPropComp from './NestedComponents/Slots/SlotPropComp.vue';
export default {
    name: 'Slots',
    components: {
        SingleSlotCard,
        MultipleSlotCard,
        SlotPropComp,
    },
    data() {
        return {
            user: {
                name: 'Anmol',
                email: 'kumaranmol888@gmail.com',
                company: 'Eli Lilly',
                workExp: '10 months',
            },
            items: [
                {
                    id: 1,
                    title: 'Apple iPhone',
                    img: '../../assets/slots/apple-iphone.jpg',
                    price: 1500
                },
                {
                    id: 2,
                    title: 'Apple iPad',
                    img: '../../assets/slots/apple-ipad.jpeg',
                    price: 900
                },
                {
                    id: 3,
                    title: 'Apple Airpods',
                    img: '../../assets/slots/apple-airpod.jpg',
                    price: 600
                },
            ],
        }
    }
}
</script>

<style scoped>
.single-slot-cards, .multiple-slot-cards, .slot-props {
    display: flex;
    flex-wrap: wrap;
}
.user-info h4, .user-image h4 {
    padding: 0;
    margin: 0;
}
.user-info hr, .user-image hr {
    color: #ddd;
}
.user-image img {
    width: 100%;
}
.multiple-slot-cards img {
    width: 100%;
}
.multiple-slot-cards .item-title {
    font-size: 16px;
    line-height: 1.3;
    font-weight: 600;
}
.multiple-slot-cards button {
    display: block;
    width: 100%;
    font-size: 14px;
    line-height: 1.3;
    padding: 8px 16px;
    border: 1px solid #999;
    border-radius: 4px;
}
.multiple-slot-cards .cart-btn {
    margin-bottom: 10px;
}
.slot-props p {
    font-size: 14px;
    line-height: 1.3;
}
.slot-props .title {
    font-size: 16px;
    font-weight: 600;
    line-height: 1.3;
}
.slot-props .author-date {
    font-size: 14px;
    line-height: 1.4;
    font-style: italic;
}
.slot-props .author-date span {
    font-weight: 600;
}
.slot-props .content {
    font-size: 15px;
    line-height: 1.5;
}
.slot-props button {
    font-size: 13px;
    font-weight: 500;
    padding: 6px 12px;
    margin-bottom: 10px;
    display: block;
    border: 1px solid #999;
}
</style>