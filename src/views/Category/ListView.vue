<template>
    <v-row class="mt-2">
        <v-icon>mdi-home</v-icon>
        <h3 class="ml-2">Danh sách loại sản phẩm</h3>
        <v-spacer></v-spacer>
        <v-btn @click="dialog=true" icon
            size="small"
            color="primary">
            <v-icon>mdi-plus</v-icon>
        </v-btn>
    </v-row>
    <v-row>
        <v-col>
            <v-card>
                <v-table>
                    <thead>
                        <tr>
                            <th>STT</th>
                            <th>Mã Loại Sản Phẩm</th>
                            <th>Tên Loại Sản Phẩm</th>
                            <th>Action</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr v-for="(item,index) in this.categories" :key="item.CategoryId">
                            <td>{{ index+1 }}</td>
                            <td>{{ item.CategoryId }}</td>
                            <td>{{ item.CategoryName }}</td>
                            <td>
                                <v-btn @click="dialogEdit=true" size="x-small" class="mr-3">
                                    <v-icon>mdi-pencil</v-icon>
                                </v-btn>
                                <v-btn size="x-small" class="mr-3">
                                    <v-icon>mdi-delete</v-icon>
                                </v-btn>
                            </td>
                        </tr>
                    </tbody>
                </v-table>
            </v-card>
        </v-col>
    </v-row>
    <add-view v-model="dialog" @close="clsoeDiaLog()" :dialog="this.dialog"></add-view>
    <edit-view  v-model="this.dialogEdit" @close="clsoeDiaLog()"></edit-view>
</template>

<script>
import axios from 'axios'
import AddView from "@/views/Category/AddView.vue"
import EditView from "@/views/Category/EditView.vue"
export default {
    name:'ListView',
    components:{AddView,EditView},
    data()
    {
        return{
            categories:[],
            dialog:false,
            dialogEdit:false,
        }
    },
    created()
    {
        this.getCategories()
    },
    methods:{
        getCategories()
        {
            axios.get('https://localhost:7125/api/Categories').then(rs=>{
                this.categories=rs.data
            }).catch(erro=>{
                console.log(erro)
            })
        },
        clsoeDiaLog()
        {
            this.dialog=false,
            this.getCategories()
            this.dialogEdit=false
        }
    }
}
</script>

<style>

</style>