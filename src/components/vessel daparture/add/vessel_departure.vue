<template>
  <div>
    <v-card>
      <v-tabs v-model="tab" background-color="normal">
        <v-tab> 1 </v-tab>
        <v-tab> 2 </v-tab>
      </v-tabs>

      <v-tabs-items v-model="tab">
        <v-tab-item v-for="item in items" :key="item.tab">
          <v-card min-height="32rem" max-height="40rem" v-if="item.tab == 1">
            <Departureform />
          </v-card>

          <v-card max-height="40rem" v-if="item.tab == 2">
            <DelayDeparture />
          </v-card>
        </v-tab-item>
      </v-tabs-items>
    </v-card>
  </div>
</template>
<style scoped></style>
<script>
import Departureform from "./Departureform.vue";
import DelayDeparture from "./DelayDeparture.vue";
export default {
  name: "Vessel_departure",
  components: { Departureform, DelayDeparture },
  props: {
    //prop pour afficher les differents forms
    formtype: String,
  },
  data() {
    return {
      tab: null,
      items: [
        { tab: "1" },
        { tab: "2" },
        { tab: "3" },
        { tab: "4" },
        { tab: "5" },
        { tab: "6" },
      ],
    };
  },
};
</script>
