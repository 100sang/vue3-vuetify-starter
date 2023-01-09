<template>
      <v-item-group selected-class="bg-primary">
          <v-row>  
            <v-col
              v-for="n in 8"
              :key="n"
              cols="3"
            >
              <v-item v-slot="{ isSelected, selectedClass, toggle }">
                <v-card
                  :class="['d-flex align-center', selectedClass]"
                  dark
                  height="150"
                  @click="toggle"
                >
                  <div
                    class="text-h6 flex-grow-1 text-center"
                  >
                    {{ isSelected ? 'Selected' : 'item'+n }}
                  </div>
                </v-card>
              </v-item>
            </v-col>
          </v-row>
      </v-item-group>
</template>

<script>

</script>

<style>

</style>
