<template>
    <v-app-bar color="primary">
        <v-app-bar-nav-icon></v-app-bar-nav-icon>
        <v-spacer></v-spacer>
        <v-toolbar-items>
            <v-btn>Hire me</v-btn>
            <v-btn>Blog</v-btn>
            <v-btn>
                <v-icon>mdi-cat</v-icon>
            </v-btn>
        </v-toolbar-items>
        <v-btn>
            <v-badge content="5" color="red">
                <v-icon>mdi-bell</v-icon>
            </v-badge>
        </v-btn>
        <v-btn>
            <v-avatar>
      <v-img
        src="https://cdn.vuetifyjs.com/images/john.jpg"
        alt="John"
      ></v-img>
    </v-avatar>
        </v-btn>
    </v-app-bar>
</template>

<script>
export default {
    name:'TopBar',
    
}
</script>

<style>

</style>