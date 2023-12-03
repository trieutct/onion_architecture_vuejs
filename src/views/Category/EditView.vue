<template>
  <v-dialog width="700px" v-model="this.dialog">
        <v-card>
            <v-card-title class="text-center">Cập nhật loại sản phẩm</v-card-title>
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
                @click="updatecategory()"
                    class="mr-2"
                    color="primary"
                >
                    Cập nhật
                </v-btn>
            </v-card-actions>
        </v-card>
    </v-dialog>
</template>

<script>
export default {
    name:'EditView',
    data()
    {
        return{
            data:{
                CategoryId:0,
                CategoryName:''
            }
        }
    },
}
</script>

<style>

</style>