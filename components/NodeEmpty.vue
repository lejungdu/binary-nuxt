<template>
<!-- eslint-disable -->
    <v-card class="node">
        <div class="emptyUser">
            <span v-if="!newUser">空いてます</span>
            <span v-else>{{ newUser }}</span>
        </div>
        <div class="emptyUserSelect">
            <v-menu offset-y>
                <template v-slot:activator="{ on, attrs }">
                    <v-btn
                        color="primary"
                        dark
                        v-bind="attrs"
                        v-on="on"
                    >
                    Dropdown
                    </v-btn>
                </template>
                <v-list>
                    <v-list-item
                        v-for="(user, index) in userList"
                        :key="index"
                        @click="selectNewUser(user)"
                    >
                    <v-list-item-title>{{ user }}</v-list-item-title>
                    </v-list-item>
                </v-list>
            </v-menu>
        </div>
        <div class="emptyUserAdd"><v-btn color="dark">メンバー追加</v-btn></div>
    </v-card>
</template>

<script>
/* eslint-disable */ 
export default {
    name: 'NodeEmpty',
    props: [ 'userList' ],
    data(){
        return {
            newUser: ""
        }
    },
    methods: {
        selectNewUser(user){
            this.newUser = user
        },
    }
}
</script>

<style scoped>
.node {
    padding: 5px 5px;
    text-align: center;
    display: inline-block;
    width: 225px;
    height: 290px;
    cursor: pointer;
    transition: 0.5s;
    margin: 0 10px;
}

.node:hover {
    box-shadow: 10px 10px 5px 0px rgba(0,0,0,0.42);
}

/* empty node layout */
.node .emptyUser {
    height: 50%;
    position: relative;
    font-size: 24px;
    font-weight: bold;
}

.node .emptyUser span {
    display: inline-block;
    width: 100%;
    position: absolute;
    top: 50%;
    transform: translate(-50%, -50%);
}

.node .emptyUserSelect, .emptyUserAdd {
    height: 25%;
    position: relative;
}

.node .emptyUserAdd button {
    position: absolute;
    top: 50%;
    transform: translate(-50%, -50%);
}

</style>