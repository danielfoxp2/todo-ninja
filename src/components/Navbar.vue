<template>
    <nav>
        <v-toolbar flat app class="white">
            <v-toolbar-side-icon class="grey--text" @click="drawer = !drawer"></v-toolbar-side-icon>
            <v-toolbar-title class="text-uppercase grey--text">
                <span class="font-weight-light">Moda</span>
                <span>Foca</span>
            </v-toolbar-title>
            <v-spacer></v-spacer>
            <v-btn flat color="grey">
                <span>Sign Out</span>
                <v-icon right>exit_to_app</v-icon>
            </v-btn>
        </v-toolbar>

        <v-navigation-drawer v-model="drawer" app class="primary">
            <p class="info">teste</p>
        </v-navigation-drawer>
    </nav>
</template>

<script>
export default {
    data() {
        return {
            drawer: false
        }
    }
}
</script>


