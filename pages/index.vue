<template>
  <div class="base">
    <h3>Simple Checkbox</h3>

    <div v-for="(data, index) in items" :key="index">
      <checkbox :data="data" v-model="selected.select" />
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  data(){
    const items = ["1","2","3","4"]
    return {
      items, 
      selected: {
        select: '',
        active: []
      }
    }
  },
  watch: {
    "selected.select"() {
      this.onCheckbox();
    }
  },
  methods: {
    onCheckbox(){
      if (this.selected.active.length == 0){
        this.selected.active.push(this.selected.select)
      }else{
        const index = this.selected.active.indexOf(this.selected.select);

        console.log(index)
        if (index > -1) {
          console.log("Hapus")
          this.selected.active.splice(index, 1);
        }else{
          this.selected.active.push(this.selected.select)
        }
      }
    }
  }
}
</script>

<style>
body, html{
  margin: 0;
  padding: 0;
  overflow: hidden;
  height: 100vh;
  width: 100vw;
  display: flex;
  align-items: center;
  justify-content: center;
}
.base{

}
</style>