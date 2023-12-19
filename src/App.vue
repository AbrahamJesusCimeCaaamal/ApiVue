<script setup>

import PostsUser from './components/PostsUser.vue';
import User from './components/User.vue';
</script>

<template >
        <div class="  bg-blue-100 " style="height: 90%;">
                <h1 class="text-2xl font-bold mb-2  text-center">Publicaciones de los usuario</h1>

                <div class="flex">
                        <div class="w-1/3 h-screen overflow-y-auto bg-gray-400">
                                <User @userSelected="mostrarPublicaciones" />
                        </div>

                        <div class="w-2/3 h-screen overflow-y-auto bg-blue-400">
                                <PostsUser :id="userIdSeleccionado" />
                        </div>
                </div>
        </div>
</template>
<script>
import PostsUser from './components/PostsUser.vue';
import User from './components/User.vue';

export default {
        components: {
                PostsUser,
                User,
        },
        data() {
                return {
                        userIdSeleccionado: null,
                };
        },
        methods: {
                mostrarPublicaciones(userId) {
                        this.userIdSeleccionado = userId;
                },
        },
};
</script>