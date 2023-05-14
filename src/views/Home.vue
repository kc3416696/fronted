<template>
    <div>
        <button @click="add()">新增商品</button><br />
        <div>產品名稱:<input type="text" v-model="ProductName" /></div>
        <div>產品價格:<input type="text" v-model="Price" /></div>
        <div>手續費率:<input type="text" v-model="FeeRate" /></div>
        <div>扣款帳號:<input type="text" v-model="Account" /></div>
        <div>購買數量:<input type="text" v-model="OrderNum" /></div>
        <table>
        </table>
    </div>
</template>

<script>
    import axios from 'axios'
    export default {
        data() {
            return {
                UserID: ""
            };
        },
        methods: {
            add() {
                axios.post('/user/add', {
                        ProductName: this.ProductName,
                        Price: this.Price,
                        FeeRate: this.FeeRate,
                        Account: this.Account,
                        OrderNum: this.OrderNum,
                    })
                    .then((res) => {
                        console.log('axios response:', res);
                    })
                    .catch((error) => {
                        console.log(error);
                    });
            }
        },
        computed: {

        },
        watch: {

        },
    }
</script>

<style>

</style>