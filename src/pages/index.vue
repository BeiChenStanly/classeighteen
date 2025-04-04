<template>
    <v-layout class="rounded rounded-md border">
        <!-- <v-app-bar color="grey-lighten-1" title="classeighteen" flat rounded>

        </v-app-bar> -->
        <v-navigation-drawer v-model="bar" :rail="rail" permanent @click="rail = false; bnticon = 'mdi-chevron-left'"
            image="https://tse1-mm.cn.bing.net/th/id/OIP-C.zpQiikU9y4h8qcUofwOuyQHaFj?rs=1&pid=ImgDetMain" theme="dark">
            <v-list-item title="十八班网站">
                <template v-slot:append>
                    <v-btn :icon="bnticon" variant="text"
                        @click.stop="rail = !rail; bnticon = bnticon === 'mdi-chevron-left' ? 'mdi-chevron-right' : 'mdi-chevron-left'"></v-btn>
                </template>
            </v-list-item>
            <v-divider></v-divider>
            <v-list density="compact" nav v-model:selected="route">
                <v-list-item prepend-icon="mdi-home-city" title="主页" value="home"></v-list-item>
                <v-list-item prepend-icon="mdi-image-multiple" title="相册" value="photos"></v-list-item>
            </v-list>
            <v-list-item bottom>
                <v-switch label="深色主题" v-model="theme.global.name.value" inset true-value="dark"
                    false-value="light"></v-switch>
            </v-list-item>
        </v-navigation-drawer>
        <v-main class="d-flex align-center justify-center">
            <v-container>
                <v-sheet border="dashed md" color="surface-light" rounded="lg" width="100%">
                    <v-card :color="color" :variant="variant" class="mx-auto" hover prepend-icon="mdi-image-multiple">
                        <v-card-title>
                            相册
                        </v-card-title>
                        <v-card-text>
                            来看看班级照片吧！
                        </v-card-text>
                        <v-carousel cycle show-arrows="hover">
                            <v-carousel-item src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
                                cover></v-carousel-item>

                            <v-carousel-item src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg"
                                cover></v-carousel-item>
                        </v-carousel>
                        <v-card-actions>
                            <v-btn color="info" href="/photo" disabled="true">进入相册</v-btn>
                        </v-card-actions>
                    </v-card>
                </v-sheet>
            </v-container>
        </v-main>
    </v-layout>
</template>
<script setup>
import { ref } from 'vue';
import { useTheme } from 'vuetify'

const theme = useTheme()
let bar = ref(true)
let rail = ref(true)
let bnticon = ref('mdi-chevron-right')
let route = ref('home')
let dark = ref(true)
</script>