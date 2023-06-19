<template>
    <v-app-bar app color="transparent" flat>

        <template v-slot:prepend>
            <!-- <v-app-bar-nav-icon size="large"></v-app-bar-nav-icon> -->
            <v-icon size="50px" icon="mdi-menu" class="ml-2" @click="drawer = !drawer"></v-icon>
        </template>

        <v-app-bar-title class="text-center"></v-app-bar-title>
    </v-app-bar>
    <v-navigation-drawer v-model="drawer" color="transparent" temporary>
        <v-list density="compact" nav>
            <v-list-item v-for="item in navigation.items" :prepend-icon="item.icon" :title="item.display" :value="item.type"></v-list-item>
        </v-list>
    </v-navigation-drawer>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
export default defineComponent({
    data() {
        return {
            drawer: false,
            navigation: {
                items: [
                    {
                        type: 'history',
                        display: 'Historia del monasterio',
                        icon: 'mdi-abacus'
                    },
                    {
                        type: 'monastery',
                        display: 'Monasterio',
                        icon: 'mdi-abacus'
                    },
                    {
                        type: 'association',
                        display: 'Asociación',
                        icon: 'mdi-abacus'
                    },
                    {
                        type: 'rooms',
                        display: 'Casa de invitados',
                        icon: 'mdi-abacus'
                    },
                    
                ]
            }
        }
    }
})
</script>