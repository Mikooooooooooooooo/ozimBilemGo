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
                    {itemName: 'Email', imageName: 'Item 1.png'},
                    {itemName: 'Crypto', imageName: 'Item 1.png'},
                    {itemName: 'Kanban', imageName: 'Item 1.png'},
                    {itemName: 'Invoicing', imageName: 'Item 1.png'},
                    {itemName: 'Banking', imageName: 'Item 1.png'},
                    {itemName: 'File Manager', imageName: 'Item 1.png'},
                    {itemName: 'User', imageName: 'Item 1.png'},
                    {itemName: 'Calendar', imageName: 'Item 1.png'},
                    {itemName: 'Todo List', imageName: 'Item 1.png'},
                ]
            };
        }
    }
</script>