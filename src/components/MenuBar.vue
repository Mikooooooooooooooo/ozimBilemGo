<template>
    <div class="menu-bar">
        <MenuItem v-for="(item, index) in elements" :key="index" :itemName="item.itemName" :imageName="item.imageName"></MenuItem>
    </div>
</template>

<script scoped>
    import MenuItem from './MenuItem.vue';

    export default{
        components:{
            MenuItem
        },
        data(){
            return{
                elements: [
                    {itemName: 'Dashboard', imageName: 'Item 1.png'},
                    {itemName: 'Email', imageName: 'Item 2.svg'},
                    {itemName: 'Crypto', imageName: 'Item 3.svg'},
                    {itemName: 'Kanban', imageName: 'Item 4.svg'},
                    {itemName: 'Invoicing', imageName: 'Item 5.svg'},
                    {itemName: 'Banking', imageName: 'Item 6.svg'},
                    {itemName: 'File Manager', imageName: 'Item 7.svg'},
                    {itemName: 'User', imageName: 'Item 8.svg'},
                    {itemName: 'Calendar', imageName: 'Item 9.svg'},
                    {itemName: 'Todo List', imageName: 'Item 10.svg'},
                ]
            };
        }
    }
</script>