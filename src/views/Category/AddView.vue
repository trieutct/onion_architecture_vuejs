<template>
    <v-dialog width="700px">
        <v-card>
            <v-card-title class="text-center">Thêm mới sản phẩm</v-card-title>
            <v-card-text>
                <v-form>
                    <v-container>
                        <v-row>
                            <v-col>
                                <v-text-field v-model="this.data.CategoryName" label="Tên loại sản phẩm"></v-text-field>
                            </v-col>
                        </v-row>
                    </v-container>
                </v-form>
            </v-card-text>
            <v-card-actions>
                <v-spacer></v-spacer>
                <v-btn
                    @click="this.$emit('close')"
                    class="mr-2"
                    color="red darken-3"
                >
                    Hủy
                </v-btn>
                <v-btn
                @click="addcategory()"
                    class="mr-2"
                    color="primary"
                >
                    Lưu
                </v-btn>
            </v-card-actions>
        </v-card>
    </v-dialog>
</template>

<script>
import axios from 'axios';
export default {
    name:'AddView',
    data()
    {
        return{
            data:{
                CategoryId:0,
                CategoryName:''
            }
        }
    },
    prop:{
        dialog:Boolean
    },
    methods:{
        addcategory()
        {
            axios.post("https://localhost:7125/api/Categories",this.data).then(rs=>{
                this.$emit('close')
            }).catch(erro=>{
                alert(erro)
            })
        }
    }
}
</script>

<style>

</style>