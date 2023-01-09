<template>
   <v-card flat class="mt-5">
        <v-list lines="two">
        <v-list-subheader>List Items</v-list-subheader>
        <template v-for="n in 5" :key="n">
            <v-list-item>
            <template v-slot:prepend>
                <v-avatar color="grey-darken-1"></v-avatar>
            </template>

            <v-list-item-title>Message {{ n }}</v-list-item-title>

            <v-list-item-subtitle>
                Lorem ipsum dolor sit amet, consectetur adipisicing elit. Nihil repellendus distinctio similique
            </v-list-item-subtitle>
            </v-list-item>

            <v-divider
            v-if="n !== 6"
            :key="`divider-${n}`"
            inset
            ></v-divider>
        </template>
        </v-list>
    </v-card>
</template>

<script>
export default {

}
</script>

<style>

</style>