<template>
    <div>
        <add-item @add-list="addList" />

        <ui class="list" v-for="item in list" :key="item.id">
            <li class="list__item">
                <item-avatar :avatar="item.avatar" />
                {{ item.name }}
                <button @click="removeItem(item.id)">
                    x
                </button>
            </li>
        </ui>
    </div>
</template>

<script>
import AddItem from "./AddItem"
import ItemAvatar from "./ItemAvatar"

const api = 'https://randomuser.me/api/?results=10'

export default {
    name: 'ItemList',
    components: {
        AddItem,
        ItemAvatar
    },
    created() {
        this.getUsers()
    },
    data() {
        return {
            list: []
        }
    },
    methods: {
        getUsers() {
            this.axios.get(api)
                .then((res) => {
                    this.list = res.data.results.map((user) => {
                        return {
                            id: user.id.value,
                            name: `${user.name.first} ${user.name.last}`,
                            avatar: user.picture.large
                        }
                    })
                })
        },
        addList(newItem) {
            let rand = Math.floor(Math.random() * Math.floor(30))

            console.log(newItem)

            this.list.push(
                {
                    id: rand,
                    name: newItem
                }
            )
        },
        removeItem(id) {
            let find = this.list.find(row => row.id == id)
            let index = this.list.indexOf(find)
            this.list.splice(index, 1);
            console.log(index)
            console.log(this.list.length)
        }
    }
}
</script>

<style scoped>
.list__item {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    list-style-type: none;
    padding: 3px;
    max-width: 200px;
}
</style>
