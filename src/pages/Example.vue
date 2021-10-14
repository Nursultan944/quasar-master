<template>
<div>
  <h2>Props & emit</h2>
  <q-btn color="purple" text-color="white" label="Open dialog modal" @click="openDialog" />
  <q-dialog v-model="isDialog">
    <DialogCards
      :message="text"
      :some-array="[1,4,8]"
      :some-boolean="true"
      :some-number="9"
      :some-obj="obj"
      :some-function="someMethod"
      @closeModalDialog="closeModal"
      @getConsole="showConLog"
    />
  </q-dialog>
</div>
</template>

<script>
import DialogCards from "components/DialogCards";
export default {
  name: "Example",
  components: {DialogCards},
  data () {
    return {
      isDialog: false,
      text: 'EXAMPLE !!!',
      obj: {
        name: 'Aidai',
        city: 'Bishkek'
      }
    }
  },
  methods: {
    openDialog () {
      this.isDialog = true
    },
    someMethod () {
      console.log('METHOD FROM PARENT COMPONENT')
    },
    closeModal (valueFromEmit) {
      this.isDialog = valueFromEmit
    },
    showConLog (text) {
      console.log(text)
    }
  }
}
</script>

<style scoped>

</style>
