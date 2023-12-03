<template>
    <v-navigation-drawer>
        <v-toolbar color="primary">
            <v-icon class="ml-2">mdi-home</v-icon>
            <v-toolbar-title>
                --LeO--
            </v-toolbar-title>
        </v-toolbar>
        <v-list density="compact">
            <v-list-item v-for="(item, i) in links" :key="i" :value="item" color="primary">
                <template v-slot:prepend>
                    <v-icon :icon="item.icon"></v-icon>
                </template>
                <v-list-item-title>{{ item.text }}</v-list-item-title>
            </v-list-item>
        </v-list>
    </v-navigation-drawer>
</template>

<script>
export default {
    name: 'SideBar',
    data() {
        return {
            links: [
                {
                    icon: 'mdi-microsoft-windows',
                    text: 'Loại sản phẩm'
                },
                {
                    icon: 'mdi-sale-outline',
                    text: 'Sản phẩm'
                },
                {
                    icon: 'mdi-cart-outline',
                    text: 'Đơn hàng'
                }
            ],
        }
    }
}
</script>

<style></style>