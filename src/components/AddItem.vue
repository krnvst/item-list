<template>
    <div>
        <input type="text" v-model="newItem">
        <button class="button" @click="addList()" >+ Add list</button>
    </div>
</template>

<script>
export default {
    name: 'ItemList',
    data() {
        return {
            newItem: '',
        }
    },
    methods: {
        addList() {
            this.$emit('add-list', this.newItem)
            this.newItem = ''
        }
    }
}
</script>

<style scoped>
    .button {
        border: none;
        padding: 4px;
        background: #555;
        color: #fff;
    }
</style>