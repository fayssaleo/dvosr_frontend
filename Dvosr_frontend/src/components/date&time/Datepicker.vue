<template>
<vc-date-picker  v-model="date" mode="dateTime" is24hr>
  <template v-slot="{ inputValue, inputEvents }">
    
       <v-text-field
       
       outlined
       :label="label"
      :value="inputValue"
      v-on="inputEvents"
  
    ></v-text-field>
  </template>
</vc-date-picker>
</template>
<style scoped>

</style>
<script>
export default {
  name: "Datepicker",
  components: {},
  props:{
      label:String
    },
  data() {
    
    return {
        date: new Date(),
    
    };
  },
  methods:{
    addToMenu(){
      this.$parent.addToMenu();
       this.$emit('datevalue', this.date);
    }
  }
};
</script>
