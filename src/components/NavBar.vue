<template>
    <div id="nav">
        <nav>
            <div>
                <ul>
                    <li
                        v-for="link in links"
                        :key="link.id">
                        <router-link 
                            :to="`${link.page}`"> {{ link.text }} </router-link>
                    </li>
            </ul>
            </div>
            <div class="cart">
                <p @add-to-cart= "updateCart"> Cart {{ cart }} </p>
            </div>
        </nav>
    </div>
</template>

<script>
    
export default {
    data() {
        return {
            links: [
                {
                    id: 1,
                    text: 'ShopOnline',
                    page: '/'
                },
                {
                    id: 2,
                    text: 'About',
                    page: '/about'
                }
            ],
            cart: 0,
            method: {
                updateCart () {
                    this.cart += 1
                }
            }
        }
    }
}
</script>

<style scoped>
    nav {
        background-color: #cccccc;
        padding: 30px;
    }
    ul {
        text-align: center;
    }
    ul > li{
        display: inline-block;
        margin-right: 20px;
        font-size: 30px
    }
    .cart {
        text-align: right;
        margin-right: 50px;
    }
</style>